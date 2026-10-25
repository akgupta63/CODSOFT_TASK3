# CODSOFT_TASK3

Customer Churn Prediction Project
This project focuses on predicting customer churn using historical customer data from a subscription-based business model. It evaluates and compares the performance of multiple machine learning classifiers to determine the best model for detecting customers at risk of leaving.

Table of Contents
Project Overview
Dataset Description
Data Preprocessing
Model Architecture
Model Evaluation Results
How to Run
Project Overview
Customer churn represents a major revenue leakage for subscription businesses. Detecting potential churners beforehand allows companies to proactively target them with retention campaigns. In this project, we implement and benchmark three popular algorithms:

Logistic Regression (Linear baseline)
Random Forest (Ensemble bagging)
Gradient Boosting (Ensemble boosting)
Dataset Description
The dataset used is Churn_Modelling.csv. It contains 10,000 customer records with the following characteristics:

Demographics: Geography, Gender, Age.
Account Metrics: Credit Score, Tenure, Account Balance, Number of Products, Estimated Salary, Active Membership Status, and Credit Card Ownership.
Target Variable: Exited (1 if the customer churned, 0 otherwise).
Data Preprocessing
To prepare the dataset for machine learning, the following pipeline was built:

Feature Dropping: Irrelevant identifier columns (RowNumber, CustomerId, Surname) were removed.
Feature Types Identification: Separated into Numerical and Categorical feature lists.
Feature Scaling: Numerical attributes were standardized using StandardScaler.
Categorical Encoding: Categorical variables (Geography, Gender) were converted into numerical values using OneHotEncoder.
Data Splitting: Split into 80% Training and 20% Testing sets using stratification to handle target imbalance.
Model Architecture
We leveraged scikit-learn's Pipeline API to bundle preprocessing and estimator training seamlessly, ensuring no data leakage occurred between training and validation steps.

Model Evaluation Results
Model	Accuracy	Recall (Class 1)	F1-Score (Class 1)	ROC AUC
Logistic Regression	81%	19%	0.28	0.7748
Random Forest	86%	46%	0.58	0.8522
Gradient Boosting	87%	49%	0.60	0.8708
Conclusion
Gradient Boosting Classifier is the champion model with the highest ROC AUC of 0.8708 and the best balance of Precision and Recall for detecting churned customers.
