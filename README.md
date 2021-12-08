# Cab_Surge_Price_Type_Prediction
## Introduction
With the upcoming cab aggregators and demand for mobility solutions, the past decade has seen immense growth in data collected from commercial vehicles with major contributors such as Uber and Ola to name a few. There are loads of innovative data science and machine learning solutions being implemented using such data and that has led to tremendous business value for such organisations.

## Business Problem
XXX Cab Private Limited company is a cab aggregator service company. Their customers can download their app on smartphones and book a cab from any where in the cities the company operates in. They, in turn search for cabs from various service providers and provide the best option to their client across available options. They have been in operation for little less than a year now. During this period, they have captured surge_pricing_type from the service providers.
The business aim is to build a predictive model, which could help them in predicting the surge_pricing_type pro-actively. This would in turn help them in matching the right cabs with the right customers quickly and efficiently.

## Proposed Solution
Deploy AI engine to predict surge price type
• Analogous to a typical classification problem
• Use existing cab trips & customer data to train the AI model
• Potential algorithms that can be explored: 
  • Logistic Regression
  • Tree-based Classification
  • BaggingAlgorithms
  • BoostingAlgorithms
  
  ## Machine Learning Modelling Steps
• Importing libraries and data
• Exploring data
• Checking for missing values
• Treating missing values by EDA
• Converting categorical columns to one-hot encoding
• Checking correlation & dropping highly correlated values
• Outlier detection & treatment
• Checking skewness of data
• Univariate, bivariate, multivariate analysis
• Scaling continuous values by Standard Scaler
• X and y assignment
• Train and test splitting (70-30)
• Training using LR, DT, RF, XGB
• Checking training accuracies
• Determining feature importance
• Prediction on Test data
• Evaluation metrics

## Input Data Exploration and Understanding
• Trip_ID is not required in building up the predictive model and so can be dropped
• The dataset has no empty values for input variables Trip_Distance, Destination_Type, Customer_Rating, Cancellation_Last_1Month, Var2, Var3, Gender
• There are no empty values in Target variable Surge_Pricing_Type
• We have some missing values in Type_of_Cab which is a categorical column with values A,B,C,D and E. For the missing values (nan), a new category ‘F’ can be created
• Customer_Since_Months are the customers using the cab service since n months. Nan values in this column can thus be replaced with 0, indicating that they are the newbies to this cab service
• Life_Style_Index and Confidence_Life_Style_Index are the Proprietary indexes created by XXX Cabs showing lifestyle of the customer based on their behaviour. EDA can be performed to replace nan values
• Var1 is a continuous variable masked by the company. Again, need to perform EDA to replace the nan values

## Data Exploration
Various plots demonstrate the distribution of data (shown in pdf)

## Model Used
Stratified K-fold Cross Validation is used to avoid changes in train accuracies each time we train the model and some proportion of each target class is there in train and validation sets.
Train Accuracies with different models are-
Logistic Regression: 69.34%
Decision Trees: 57.37%
Random Forest: 69.31%
XGBoost: 70.19%
Highest train accuracies are achieved with XGBoost so we can further try enhancing the accuracies by hyper-parameter optimisation of XGBoost.

## Test Accuracy
Test Accuracies with different models are-
LR: 68.86%
DT: 57.75%
RF: 69.19%
XGB: 69.98%

## Hyperparameter Optimization
Optimising the hyper parameters, we are able to enhance the train accuracy of XGB to 70.29%.
New Test Accuracy of XGB after hyper parameter optimisation -
XGB: 70.07%
