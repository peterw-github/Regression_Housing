# Housing Regression Project

<br>

Hello! 

This is a project, whereby I attempted to **predict housing prices**, based off of a large number of features (79 initially, through processing, cleaning, and encoding categorical variables, the number of features did change, ending up at 219, mainly due to one-hot encoding). 1460 homes total are involved in the dataset, split 80% into training, and 20% into testing.

<br>
<br>

**Quick Walkthrough:**

Once the data was cleaned, and explored, modelling was performed, initially starting off with standard Multivariable Linear Regression. The model seemed fairly decent, but unfortunately there were 2 extreme outliers (the amount varies depending on what data ends up in the training set, from SKlearns train_test_split function), that plagued the model. 

I suspected this outlier issue, was due to multi-collinearity between the categorical features (them being highly linearly correlated either to each other, or to the rest of the non-target features in the dataset), and thus employed Ridge Regression. I decided on Ridge Regression, as it was designed to deal with datasets that have a potentially large number of features, that are highly linearly correlated to each other, the exact problem I thought standard linear regression was encountering.

Ridge regression worked out nicely, solving the extreme outlier problem fairly well, and performing overall decently IMO.

The **results of the Ridge Regression model** is here:

<br>

[<img alt="Ridge Regression Performance" width="700" height=400 src="./images/RidgeResults.PNG" />]()

<br>

The Ridge model **predicted the sale price of 292 different homes, and on average, was off by about $13,830, according to Mean Absolute Error (MAE), or $22,353 if using Remote Mean Squared Error (RMSE), which is more sensitive to outliers.**

Predicting, and being off on average, by about 14 or 23 thousand dollars either way, does seem like a lot of money, but proportionally speaking, the median sale price amongst all 1460 houses in the dataset, was $163,000. So **MAE / RMSE are 9% and 14% of the size of the median**, which isn't too bad IMO, especially considering that the specific outlier issue is still affecting Ridge to an extent, but there is certainly a lot of room for improvement. 

In order to achieve those improvements, two immediate things come to mind:

1. Eliminating/reducing the multi-collinearity that is still present amongst the categorical features, which is causing outlier issues.

3. Testing out other models (such as a decision tree or a model ensemble like a random forest, as these forms of models are quite different to linear regression, and don't use gradient descent as a means of improvement, local minima issues could be decreasing the performance of our Linear / Ridge regression models at the moment)

<br>
<br>
<br>

A thorough walkthrough of my analysis of the dataset, can be found in the Jupyter Notebook file,"HousePrices_Regression.ipynb", which includes descriptions of what I'm doing, as I go through the analysis.

This project was based off of the popular Ames housing price dataset, available on Kaggle, here:  
https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/overview

*Note: data.csv is simply the dataset used, and data_desc.txt, just contains detailed descriptions, of each of the 81 features total, in the dataset.*




