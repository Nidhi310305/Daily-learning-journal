# 2026-06-25 — Housing Price Prediction using Linear Regression

## Learning Objectives

* Apply Linear Regression to a real-world housing dataset.
* Strengthen understanding of data preprocessing and feature analysis.
* Investigate the impact of multicollinearity on model performance.
* Evaluate a regression model using standard performance metrics.

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

Linear Regression is a supervised learning algorithm used to model the relationship between input features and a continuous target variable. In this project, it was used to estimate housing prices based on available property characteristics.

### Exploratory Data Analysis

Initial dataset exploration was performed to understand feature distributions, identify potential data quality issues, and gain familiarity with the dataset before model development.

### Multicollinearity and VIF

Variance Inflation Factor (VIF) analysis was used to identify highly correlated independent variables. Reducing multicollinearity helps improve model interpretability and stability.

### Model Evaluation

Model performance was evaluated using the R² score to measure how effectively the model explained variance in housing prices.

## Practical Work

* Loaded and inspected the housing dataset.
* Performed data quality checks, including missing value and duplicate analysis.
* Explored feature relationships and distributions.
* Processed date-related attributes for analysis.
* Identified and analyzed potential outliers.
* Calculated VIF scores to assess multicollinearity.
* Removed or evaluated highly correlated features.
* Split the dataset into training and testing subsets.
* Trained a Linear Regression model using Scikit-learn.
* Generated predictions on unseen data.
* Evaluated model performance using regression metrics and visual comparisons between actual and predicted values.

## Challenges

* Understanding the effect of correlated features on regression performance.
* Interpreting VIF values and selecting appropriate features for the final model.
* Connecting preprocessing decisions to model accuracy and interpretability.

## Next Steps

* Study regularization techniques such as Ridge and Lasso Regression.
* Compare model performance with alternative regression algorithms.
* Explore additional evaluation metrics including MAE, MSE, and RMSE.
* Investigate feature importance and model interpretability techniques.

## Reflection

This project reinforced the importance of data preparation before model training. While Linear Regression itself is straightforward to implement, the quality of the results depends heavily on understanding the dataset, identifying feature relationships, and addressing multicollinearity. The exercise provided practical experience with a complete regression workflow, from data exploration through model evaluation.

## Quick Revision Notes

- Linear Regression predicts continuous numerical values.
- Data quality and feature selection significantly impact model performance.
- Train-test split is used to evaluate model generalization on unseen data.
- Multicollinearity can negatively affect model interpretability.
- Variance Inflation Factor (VIF) helps identify highly correlated features.
- R² Score measures the proportion of variance explained by the model.
- Feature engineering and preprocessing are often as important as model selection.

## Resources

### Notebook

 - [Housing Prediction Notebook](Housing_Prediction.ipynb)

### Related Learning Entries

- [2026-06-15 — Linear Regression on Insurance Dataset](2026-06-15-linear-regression-insurance-dataset.md)

### Key Libraries Used

- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
