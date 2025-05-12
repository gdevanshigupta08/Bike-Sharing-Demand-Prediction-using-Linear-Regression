# Bike Sharing Demand Prediction using Linear Regression

## Project Overview
This project focuses on building and interpreting a Linear Regression model to predict the daily demand for shared bikes operated by BoomBikes, a US bike-sharing provider. Facing significant revenue dips due to the COVID-19 pandemic, BoomBikes aims to understand the key factors driving bike usage as conditions normalize. The analysis leverages historical daily data (`day.csv`), encompassing seasonal information, weather conditions, and calendar attributes from 2011-2012. The primary goal is not only to predict the total daily bike rentals (`cnt`) but also to identify the most significant predictor variables and quantify their impact on demand. This involves a structured approach including data cleaning, exploratory data analysis (EDA), feature engineering (handling categorical variables, scaling), and robust model building using linear regression with careful feature selection techniques (RFE, p-values, VIF) to ensure model interpretability and reliability. The insights gained are intended to help BoomBikes optimize operations, strategize effectively for market recovery, and gain a competitive advantage.

## Problem Statement
BoomBikes experienced revenue challenges due to the COVID-19 pandemic. To prepare for the post-quarantine market and optimize operations, the company needs to understand the significant variables predicting bike demand. This model helps identify these key drivers and explains how well they predict the total daily bike rentals (`cnt`).

## Methodology

1.  **Data Loading and Cleaning:** Loaded the `day.csv` dataset, dropped irrelevant columns (`instant`, `dteday`, `casual`, `registered`), renamed columns for clarity, and mapped categorical variables to meaningful labels.

2.  **Exploratory Data Analysis (EDA):** Visualized relationships between the target variable (`cnt`) and various predictor variables (numerical and categorical) using pairplots, heatmaps, and boxplots.

3.  **Data Preparation:** Created dummy variables for categorical features (`season`, `mnth`, `weekday`, `weathersit`). Split the data into training and testing sets.

4.  **Feature Scaling:** Applied MinMaxScaler to numerical features (`temp`, `hum`, `windspeed`) to bring them to a comparable scale.

5.  **Model Building:**
    * Utilized Linear Regression using `statsmodels.api` and `sklearn.linear_model`.
    * Implemented Recursive Feature Elimination (RFE) for initial feature selection.
    * Refined the model iteratively by evaluating feature significance (p-values) and multicollinearity (Variance Inflation Factor - VIF), dropping less significant or highly collinear features.

6.  **Model Evaluation:** Assessed the final model's performance using R-squared and Adjusted R-squared on both training and testing data. Conducted residual analysis (checking for normality and homoscedasticity) to validate model assumptions.

## Key Findings

The final linear regression model identified several significant predictors of daily bike demand, including:
* **Positive Influences:** Temperature (`temp`), Year (`yr` - indicating growth over time), specific months/seasons (e.g., Fall, September).
* **Negative Influences:** Bad weather situations (`Light_snowrain`, `Misty`), high windspeed (`windspeed`), holidays (`holiday`), specific seasons (e.g., Spring).

The model explains a significant portion of the variance in bike demand (refer to R-squared values in the notebook).


