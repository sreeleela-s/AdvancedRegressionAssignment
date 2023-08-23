# Predicting factors influencing Sale Price for US-based housing company, Surprise Housing
> Need to create a model the predicts the factors that influence sale price of a house for US-based housing company Surprise Housing. IThe company uses data analytics to purchase houses at a price below their actual values and flip them on at a higher price.The company want's to use a regularization based regression model in order to predict the actual value of the prospective properties and decide whether to invest in them or not.


## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
1. BUSINESS GOAL:
Model the price of houses with the available independent variables. This model will then be used by the management to understand how exactly the prices vary with the variables. They can accordingly manipulate the strategy of the firm and concentrate on areas that will yield high returns. Further, the model will be a good way for management to understand the pricing dynamics of a new market.
2. Data set  Understanding:
  1. We can see that null values are present in LotFrontage,Alley,MasVnrType,MasVnrArea,BsmtQual,BsmtCond,BsmtExposure,BsmtFinType1,Electrical,FireplaceQu,GarageType,GarageYrBlt,GarageFinish,GarageQual,GarageCond,PoolQC,Fence,MiscFeature
  2. If we check the data dictionary closely, we can see that there are not null values, NA there is one of the categorical variable meaning 'no fence','no pool' etc., Need to take care of this in data cleaning.
  3. Data is about the sales made between the years 2006 and 2010.
  4. SalePrice is the variable we are interested in predicting based on other variables in the 	data.Since its a continous variable we can proceed with regression.
  5. Data has almost 47 categorical variables. More than half of the columns.
  f. The propery sales are at different neighbourhoods with in Ames city limits.

## Conclusions
Metric-REF+LR,REF+Ridge,Ridge,Lasso 
1. 	R2 Score (Train)-0.875405(REF+LR),0.87505(REF+Ridge),0.941217(Ridge),0.940837(Lasso)
2.	R2 Score (Test)-0.776238(REF+LR),0.782056(REF+Ridge),0.882637(Ridge),0.887635(Lasso)
3.	RSS (Train)-3.692802(REF+LR),3.7033(REF+Ridge),1.742219(Ridge),1.753497(Lasso)
4. 	RSS (Test)-2.907332(REF+LR),2.831742(REF+Ridge),1.524892(Ridge),1.459955(Lasso)
5.  MSE (Train)-0.065414(REF+LR),0.065507(REF+Ridge),0.044931(Ridge),0.045076(Lasso)
6.	MSE (Test)-0.088643(REF+LR),0.087483(REF+Ridge),0.064198(Ridge),0.062816(Lasso)


Observations:
As we can see , Ridge regression without RFE and Lasso models seem to perform better.

## Insights 
Observations:
1. We can notice that Ground Floor Living area is the dominant factor in all the models.
2. We also see that House Age is a negative indicator for price. As the age of the house goes up, price goes down
3. High Over all quality(8,9,10) is one of the prominent predictors in all the models.
4. Followed by Total basement Area , Good over all condition and lot Area ,which also are seen in all the models with decent beta values. They carry considerable weight in predicting the overall price of the house.

## Technologies Used
I have imported the below libraries as part of the assignment:
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn import linear_model, metrics
from sklearn.linear_model import LinearRegression
from sklearn.linear_model import Ridge
from sklearn.linear_model import Lasso
from sklearn.model_selection import GridSearchCV
from sklearn.metrics import mean_squared_error, r2_score
from sklearn import metrics
import statsmodels.api as sm #for add the constant value
from sklearn.preprocessing import MinMaxScaler #for performing minmax scaling on the continous variables of training data
from sklearn.model_selection import train_test_split #for spliting the data in terms of train and test

from statsmodels.stats.outliers_influence import variance_inflation_factor #to calculate the VIF
from sklearn.metrics import mean_squared_error #for calculating the mean squared error

from sklearn.feature_selection import RFE
from sklearn.linear_model import LinearRegression

## Acknowledgements
Appreciate the course content by Upgrad and IIIT Bangalore , helping me analyse this data


## Contact
Created by [@sreeleela-s] - feel free to contact me!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
