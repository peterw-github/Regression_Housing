# Housing Regression Project

Hello! 

This is a project, whereby I attempted to **predict housing prices**, based off of a large number of features (79 initially, through processing, cleaning, and encoding categorical variables, the number of features did change, ending up at 219, mainly due to one-hot encoding). 1460 homes total are involved in the dataset, split 80% into training, and 20% into testing.


**Quick Walkthrough:**

Once the data was cleaned, and explored, modelling was performed, initially starting off with standard Multivariable Linear Regression. The model seemed fairly decent, but unfortunately there were about 3-6 extreme outliers (depending on what data ends up in the training set, from SKlearns train_test_split function), that plagued the model. 

I suspected it was due to multi-collinearity between the categorical features (them being highly linearly correlated either to each other, or to the rest of the non-target features in the dataset), and thus employed Ridge Regression. I decided on Ridge Regression, as it was designed to deal with datasets that have a potentially large number of features, that are highly linearly correlated to each other, the exact problem I thought standard linear regression was encountering.

Ridge regression worked out very nicely, solving the extreme outlier problem, and performing overall fairly well IMO (for a basic model, this project didn't involve any  random forests, or any other model ensembles). 

The **results of the Ridge Regression model** is here:

<br>

![Ridge Regression Performance](images/RidgePerformance.PNG)\

<br>

A thorough walkthrough of my analysis of the dataset, can be found in the actual Jupyter Notebook file,"HousePrices_Regression.ipynb", which includes descriptions of what I'm doing, as I do it.

This project was based off of the popular Ames housing price dataset, available on Kaggle, here:
https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/overview




