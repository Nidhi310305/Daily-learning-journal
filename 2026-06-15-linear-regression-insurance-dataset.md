# 2026-06-13 — Linear Regression on Insurance Dataset

## Learning Objectives

* Understand the end-to-end workflow of a supervised machine learning project.
* Apply Linear Regression to a real-world dataset.
* Explore data preprocessing and feature selection techniques.
* Evaluate model performance using standard regression metrics.

## Topics Studied

* Linear Regression
* Exploratory Data Analysis (EDA)
* Data Cleaning
* Feature Engineering
* Multicollinearity
* Variance Inflation Factor (VIF)
* Train-Test Split
* Model Evaluation

## Key Concepts

### Linear Regression

Linear Regression is a supervised learning algorithm used to model the relationship between independent variables and a continuous target variable.

### Exploratory Data Analysis

Performed initial dataset inspection to understand feature distributions, dataset dimensions, and feature characteristics before model development.

### Multicollinearity and VIF

Studied the impact of highly correlated independent variables on model performance. Used Variance Inflation Factor (VIF) analysis to identify and remove features contributing to multicollinearity.

### Model Evaluation

Evaluated model performance using the R² Score, which measures how effectively the model explains variance in the target variable.

## Practical Work

* Loaded and explored the insurance dataset.
* Examined dataset structure and feature distributions.
* Investigated categorical and numerical attributes.
* Performed data quality checks, including null value inspection.
* Analyzed feature relationships and dependencies.
* Calculated VIF scores to identify multicollinearity.
* Removed highly correlated features based on VIF analysis.
* Split the dataset into training and testing sets.
* Trained a Linear Regression model using Scikit-learn.
* Generated predictions on the test dataset.
* Evaluated model performance using R² Score.

## Challenges

* Understanding how multicollinearity affects regression models.
* Interpreting VIF values and determining which features should be removed.
* Connecting preprocessing decisions to model performance.

## Next Steps

* Study the assumptions of Linear Regression in greater depth.
* Explore Multiple Linear Regression with additional feature combinations.
* Compare Linear Regression with regularized models such as Ridge and Lasso Regression.
* Investigate additional regression evaluation metrics such as MAE, MSE, and RMSE.

## Reflection

This exercise provided practical exposure to the complete machine learning workflow rather than focusing solely on model training. The most valuable learning outcome was understanding the importance of data preparation and feature selection before model development. The use of VIF analysis highlighted how feature relationships can influence model stability and interpretability.

## Quick Revision Notes

- Linear Regression predicts continuous values.
- Train-test split helps evaluate generalization.
- VIF can identify multicollinearity.
- R² measures explained variance.

- ## Resources

- Google Colab Notebook: [Open Notebook](https://colab.research.google.com/drive/14eUHAz-UB-VU23Ei8Ty5k-vhKvNhOA8w?usp=sharing)
