# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 4 West Nile Virus Prediction

_Team Members: Evonne, Graham, Rong Wong_

![](https://www.vdci.net/hs-fs/hubfs/Vector_Borne_Disease_Education_Protecting_Public_Health-banner.png?width=1840&name=Vector_Borne_Disease_Education_Protecting_Public_Health-banner.png)

## Problem Statement

West Nile virus (WNV) is the leading cause of mosquito-borne disease in the continental United States.  It is most commonly spread to people by the bite of an infected mosquito. There are no vaccines to prevent or medications to treat WNV in people

In order to maximise control of adult mosquito populations with spray airborne pesticides, we will predict when and where different species of mosquitos will test positive for West Nile virus. This will help the City of Chicago and CPHD more efficiently and effectively allocate resources towards preventing transmission of this potentially deadly virus. 

Success is evaluated using AUC-ROC curve between the predicted probability that West Nile Virus is present and the observed outcomes.

## Executive Summary

Utilizing weather, geographic, and mosquito collection data from Chicago that was analyzed, cleaned, processed and ran through several classification models. 

This was followed by creating, cross-validating and evaluating multiple classifier models. We found that the Extreme Gradient Boosting model was best suited to predicting instances of WNV, since it was able to perform well with an ROC AUC score of 0.7378.

We also saw that the top features of this model related not only to particular locations/traps, but also to specific weather features, owing to the relationship between mosquito breeding, temperature rises and humidity.
Finally, a cost-benefit analysis was run examining the impact of spraying (or not spraying) pesticides in Chicago specifically in 2020, before expanding upon the subject and making realistic notes about the assumptions we made (and didn’t make). We also offered a 3-pronged solution to help address the WNV issue.

## Project Planning
Deliverables: our end result is 1)a predictive "Extreme" Gradient Boosting model to predict the presence of WNV, as well as 2) a cost benefit analysis examining whether spraying is justified as a primary means for transmission control. 3) We also recommend extraneous solutions based on external research to the CDC, culminating in a group presentation to our stakeholders, the CDC.

To achieve these deliverables, we have broken up components and assigned workflow, with progress tracked on Github's native project management tool in our repo. Task assignment is based on key milestones, as follows:
* Rong Wong: Cleaning, and EDA Part 1
* Evonne: EDA Part 2, Feature Engineering and Pre-processing
* Graham: Modelling Evaluation and Selection, Cost-Benefit Analysis + Recommendations
* All: Presentation


## Data

The data dictionary can be found in this [link](https://www.kaggle.com/c/predict-west-nile-virus/data)

- Weather Data from 2007-05-01 to 2014-10-31
- Spray Data from 2011-08-29 to 2013-09-05
- Train Data from 2007-05-29 to 2013-09-26
- Test Data from 2008-06-11 to 2014-10-02


## Conclusion and Recommendation 
Using Extreme Gradient Boosting model (our best performing model), we achieved the AUC score of 0.7378 and a auc_cross_val_score on our production model, which shows a really high mean cross validation score of 0.8181.

Month of the year, August, June and July (which are the hottest months in Chicago) were the top predictor by far for our model, That seasonality is also why Station Pressure - or higher atmospheric pressure in the weather - also is a top feature, as is Average Temperature, and Relative Humidity - with hotter and moister conditions encouraging mosquitoes and the virus. In other words, the weather really matters in predicting the virus.
We also see certain traps we saw in our previous EDA are indeed top traps like Trap T900, or Trap T115, and that the main carriers for WNV are the Culex Restuans and Pipiens.
Therefore spray efforts should be concentrated during this period in these areas.

After conducting a cost-benefit analysis, there are 3 recommendations we make to address this shortcoming: 
- Firstly, we should re-target specific WNV clusters that were missed out by spraying, as well as take special care to target clusters around our Top Traps and Top WNV Addresses - both of which we have already discussed. These are high-occurrence areas that are particularly virulent, and it would maximize the value of the amount invested in spraying.
- Secondly, we recall that many Weather features accelerate mosquito breeding. We already saw earlier that hot and humid months (June, July, August and September) are the strongest catalysts for WNV, because such months are prime breeding periods for mosquitoes. For maximum effect, we could suggest that spraying be intensified during those particular months.
- Lastly, apart from spraying, we can adopt other concurrent campaigns targeted at mosquito breeding and transmission prevention best practices. For example, this would include CDC advisories recommending the removal of stagnant water, the usage of mosquito repellant, and wearing long sleeved clothing to prevent bites. If we can educate more of the local population to become harder mosquito targets and reduce transmission on their own cost, this would be a win-win for the CDC and Chicago.


Sources:
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3322011/#:~:text=Total%20epidemic%20costs%20were%20≈,and%20public%20health%20agency%20costs.
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3945683/
https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0227160#pone-0227160-t002
https://www.inflationtool.com/us-dollar/2012-to-present-value
