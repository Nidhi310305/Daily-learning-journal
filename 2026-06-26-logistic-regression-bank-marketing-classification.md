# 2026-06-26 — Bank Marketing Classification using Logistic Regression

**Domain:** Machine Learning

**Dataset:** Bank Marketing Dataset

**Algorithm:** Logistic Regression

**Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn

**Type:** Hands-on Classification Implementation

---

## Learning Objectives

* Understand the workflow of a binary classification problem using Logistic Regression.
* Explore data preprocessing techniques for mixed numerical and categorical datasets.
* Apply feature engineering and multicollinearity analysis before model training.
* Evaluate classification performance using standard machine learning metrics.

---

## Topics Studied

* Logistic Regression
* Binary Classification
* Exploratory Data Analysis (EDA)
* Missing Value Handling
* Duplicate Removal
* Outlier Detection (IQR)
* Label Encoding
* Correlation Analysis
* Multicollinearity
* Variance Inflation Factor (VIF)
* Train-Test Split
* Model Evaluation

---

## Key Concepts

### Logistic Regression

Logistic Regression is a supervised machine learning algorithm used for binary classification tasks. Instead of predicting continuous values, it estimates the probability that an observation belongs to a particular class.

### Data Preprocessing

The dataset was prepared by handling missing values, removing duplicate records, encoding categorical variables, and treating outliers to improve data quality before model training.

### Feature Engineering

Correlation analysis and Variance Inflation Factor (VIF) were used to identify highly correlated features. Features contributing to multicollinearity were removed to improve model stability.

### Model Evaluation

The trained model was evaluated using prediction accuracy on unseen test data to assess its classification performance.

---

## Practical Work

* Loaded and explored the Bank Marketing dataset.
* Examined feature types and dataset structure.
* Checked for missing values and duplicate records.
* Applied IQR-based outlier treatment.
* Encoded categorical variables using Label Encoding.
* Generated a correlation matrix and heatmap.
* Calculated VIF scores to detect multicollinearity.
* Removed highly correlated features iteratively.
* Split the dataset into training and testing subsets.
* Trained a Logistic Regression classifier using Scikit-learn.
* Generated predictions on the test dataset.
* Evaluated model performance using classification accuracy.

---

## Challenges

* Understanding the difference between regression and classification workflows.
* Determining which features should be removed based on VIF analysis.
* Applying preprocessing techniques suitable for mixed-type datasets.

---

## Quick Revision Notes

* Logistic Regression is used for binary classification problems.
* The algorithm predicts class probabilities rather than continuous values.
* Label Encoding converts categorical values into numerical representations.
* VIF helps identify multicollinearity among independent variables.
* Proper preprocessing has a significant impact on classification performance.
* Accuracy measures the proportion of correctly classified observations.

---

## Resources

### Notebook

* [Logistic Regression Notebook](Logistic_Regression.ipynb)

### Related Learning Entries

* [Linear Regression on Insurance Dataset](2026-06-15-linear-regression-insurance-dataset.md)
* [Housing Price Prediction using Linear Regression](2026-06-25-housing-price-prediction-linear-regression.md)

### Key Libraries Used

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

---

## Next Steps

* Study the Sigmoid Function in greater detail.
* Understand the Confusion Matrix, Precision, Recall, and F1-Score.
* Compare Logistic Regression with Naive Bayes for binary classification tasks.
* Explore ROC Curve and AUC as additional evaluation metrics.

---

## Reflection

This exercise introduced the complete workflow of a binary classification problem using Logistic Regression. Beyond model implementation, it reinforced the importance of data preprocessing, feature engineering, and multicollinearity analysis in building reliable classification models. It also highlighted the distinction between regression and classification algorithms through practical application.
