# Regression_Project
Create a linear model regression to predict base salary for NYC employees

Introduction We got our dataset from NYC Open Data (https://data.cityofnewyork.us/City-Government/Payroll/4zc2-cuvr). Our data set contained 3,333,080 observations for the fiscal years of 2015-2019. We wanted to learn what factors contributed the most towards an employees base salary.

## Data Cleaning

For our data we dropped columns that were irrelevant to our predictor such as Last Name, First Name, Mid Init, and Payroll Number. Some columns were variable overlap so we dropped Regular Gross Paid and Total Other Pay. Lastly we dropped column with high variability such as Title Description. We created new variables by turning Agency Start Date to years worked. From there we dropped everyone that was not a salary based, working in the 4 main boroughs (not Staten Island because it was not in the dataset) and not on leave.

## EDA

$10,000 increase in average city employee salary over the past 5 years. 

Average pay by borough worked Bronx $64,444 Brooklyn $65,521 Manhattan $72,903 Queens $68,192 
![](images/salary_borough.png)

20 years is where the average pay usually levels off and that is because a lot of employees pension kicks in at that point and people retire.
![](images/salary_yearsworked.png)

The highest paying agency is the Office of Collective Bargaining
![](images/salary_agencies.png)

## Feature Engineering & Selection

Scaled continuous variables by normalizing. Looked for linear relationship between normalized variables and base salary and realized that if base salary is logged then they will be more linear. Next we split our data into test, train, split and used them to create and test our models. We created Ridge, Lasso and Linear Regression models. After comparing the residual sum mean squared errors we noticed that the Ridge model performed sightly better than Linear. Finally we did a K fold test to determine the best alpha.

## Model

Used an alpha of .01 that had a slightly lower residual sum mean squared error. Our model predicted the test data within .634 standard deviations.
![](images/Predictions.png)

## Take away
To make the maximum amount of money working for the city working for around 20 years in Manhattan for the Office of Collective Bargaining
