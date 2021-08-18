# Verve Group data science case study - answers

Thank you for the interest in my application for the Data Scientist position. Please find below the answers to the tasks you asked me to complete

## Problems that might make the building a classification model difficult

- Frequency for the target variable is unbalanced: 72% male, 28% female
- Same thing for the click feature: the relative frequency shows a very imbalanced distribution: 0.5% Yes and 99.5% No
- The app category is also imbalanced: 80% of the data is related to only 2 app_categories (News and Wheather) out of 10
- 1.7% of the events in the dataset are'nt related to any category
- Interacting with the app - the distribution is right skewed - there are also some outliers: interactions that lasted close to 100 minutes for example

## Identifying important features

I would try to identify the most important features of my model by using a logistic regression , having the gender as the target variable. The "interaction_with_app" will be the numeric  predictor, and each app_cattegory (each possible value of the app_category column) will be transformed into a binary predictor. We will use those binary predictors as dummy variables in the logistic regression model. I will do the same for each add_category (each possible value of the add_category column) but the values for eah dummy variable is going to be given by the "click" column. The most important features are the ones with the highest "risk factor" values (exponentiated slopes or Beta coefficients). 

## Model to be used: advantages and disadvantages

I will use the regression model presented on point 2. One of the advantages of using this models is that we can accurately evaluate the impact of each feature on the target variable. By looking at the risk factrs we will know how much the chances of "the user being a woman" will increase when the feature's value increases with one unit (and holding other predictors constant). 
The disadvantage is represented by the imbalance found in the target variable's frequency (there are twice as many males than females in the dataset). In order to solve this issue we will need either to drop some data or to create synthetic data (events that never took place). Also, the high number of features (created by using the dummy variables explained on point 2).
