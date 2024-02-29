# **Predicting Taxi Fares Before the Ride and Taxi Gratuities in New York City**

This project consists of 2 jupyter notebooks:
1. ["Automatica_LinearRegression.ipynb"](https://github.com/fadhlifadh/Automatidata/blob/main/Automatica_LinearRegression.ipynb)
  - This is to demonstrate data cleaning, EDA and how multi linear regression model is built
2. [Automatica_RandomForest.ipynb](https://github.com/fadhlifadh/Automatidata/blob/main/Automatica_RandomForest.ipynb)
  - This is to demonstrate how random forest model is built

For the data dictionary, please refer to [Data Dictionary](https://github.com/fadhlifadh/Automatidata/blob/main/Data_Dictionary.ipynb)

## Overview
The goal of this project was to build a multiple linear regression to predict taxi fares before the ride and
to build random forest model to predict high customer gratuity or not. 

In the other words, the taxi drivers would at least receive the estimation amount of taxi fares after the customers manage
to hop in and state their drop off location. The final multiple linear regression performed quite well with R<sup>2</sup> 
value of 0.868. This means that 86.8% of the variance in the fare_amount variable is described by the model. In simple words,
the model managed to interpret that for every 1 mile traveled, the fare increased by a mean of $2.00.

Also, for the high customer gratuity, the taxi drivers would receive alert from the app about the customers who are 
likely to tip, since drivers depend on tips. The final XGBoost model performed with 70.62% accuracy and 68.65% precision. 
Based on the model, vendorID feature were most influential in determining a generous tipper (>20%) vs a non-generous one (<20%). 

## Business Understanding
According to salary.com the average salary for a New York Taxi Driver is around $38,707 (Please note, this data might not
reflects the real salary which was in 2017). This salary is significantly low compared to a median rent value of $3,671 
per month. It is important to understand what factors encourage riders to leave tips in order to help drivers obtain a 
livable wage. 

## Business Understanding
The NYC Taxi and Limousine Commission data came from [NYC.gov](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page).
The data recorded in this case study has 22,699 rows with 18 features. The features included the information of vendor, pickup
and dropoff time, amount of tip as well as fare amount etc. From exploratory data analysis (EDA) activity, a lot of outliers
mainly on the amount of fare feature have been ellimated in order to come up with a more reasonable data for modelling purpose.
Some of the features which we think were redundant were dropped,

## Modeling and Evaluation 
The built model on multiple linear regression shows that every 1 mile traveled, the fare increased by a mean on $2.00.
The model performance on test data is as below:
1. Coefficient of determination: 0.868
2. R^2: 0.868
3. MAE: 2.133
4. MSE: 14.326
5. RMSE: 3.785
 
This means that 86.8% of the variance in the fare_amount variable is described by the model.

Meanwhile, for the random forest model, the champion model is XGBoost Classifier model with the below score:
1. Precision: 0.6864
2. Recall: 0.8133
3. F1: 0.7445
4. Accuracy: 0.7062

We know that VendorID is the most important features, but we don't know how they influence tipping.
This would require further exploration and it is interesting that VendorID is the most predictive feature.
This seems to indicate that one of the two vendors tends to attract more generous customers. It may be worth performing
statistical tests on the different vendors to examine this further in the future.

## Conclusion
These models can benefit taxi divers in knowing the estimation of fare price as well as if they will be tipped generously
or not. However, in addition to the original data, adding more information on a rider’s past tipping behavior may also be 
beneficial in helping the stakeholder address their business problem. 
