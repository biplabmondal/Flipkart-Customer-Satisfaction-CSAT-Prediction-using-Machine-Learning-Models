# Flipkart Customer Satisfaction (CSAT) Prediction using Machine Learning Models

**Project Overview**

This project is based on customer support data from Flipkart, one of India’s leading e-commerce platforms. The objective is to build a predictive machine learning model that can classify Customer Satisfaction (CSAT) scores based on historical customer interaction data. Accurate CSAT prediction enables proactive issue resolution, improves customer retention, and enhances operational efficiency in customer service.

This project focuses on analyzing customer support interaction data (85,907 records, 20 features) to:

1.Identify factors influencing CSAT scores
2.Perform exploratory data analysis (EDA)
3.Conduct hypothesis testing
4.Engineer features and handle imbalanced data
5.Build and evaluate multiple machine learning models
6.Select the best-performing model for final deployment
7.The final goal is to support business decision-making by predicting customer satisfaction outcomes in advance.

**Objectives**

CSAT Prediction - Develop a classification model to predict Customer Satisfaction Scores (1–5).

Customer Experience Insights - Identify operational and behavioral factors affecting customer satisfaction.

Operational Optimization - Improve customer support efficiency by analyzing:
Handling time
Communication channels
Agent shifts
Product categories

Business Impact - Enable proactive intervention for dissatisfied customers to reduce churn risk.

**Steps to Solve the Problem**

Problem Identification - Flipkart handles a high volume of customer queries daily (returns, cancellations, order issues, product concerns).
The challenge - Understanding what drives CSAT and how to predict dissatisfaction early.

Data Understanding:
Dataset contains -
Unique ID
Channel Name (Inbound / Email / Outcall)
Category & Sub-category
Customer Remarks
Order ID
Order & Issue timestamps
Agent Shift
Tenure Bucket
Handling Time
CSAT Score (Target Variable: 1–5)

Data Preprocessing:
Missing Value Handling
Dropped columns with >80% missing values
Median imputation for numeric features
Mode imputation for categorical features

Outlier Treatment -
IQR method (capping extreme values)

Encoding -
Label Encoding (ordinal features)
One-Hot Encoding (nominal features)

Feature Scaling - 
StandardScaler applied to numeric variables

**Exploratory Data Analysis (EDA)**

Key insights:
Most products purchased were under ₹14,000
Majority of customer interactions were Inbound calls
High CSAT (score 5) dominates dataset (~70%)
Mobile, Electronics, Furniture & Home Appliances were top categories
Handling time differs across communication channels
CSAT trend improved over time

**Hypothesis Testing:**
Test 1
H0: Average handling time is same for Email and Call
Test Used: Independent Two-Sample t-test
Test 2
H0: Average CSAT score is same for Day & Night shifts
Test Used: Welch’s t-test
These tests helped validate statistically significant differences in operational factors.

**Handling Imbalanced Dataset:**
The dataset was highly imbalanced:
CSAT 5 ≈ 70%
CSAT 1–4 underrepresented
Technique Used:
SMOTE (Synthetic Minority Oversampling Technique)
This improved minority class learning and boosted recall & F1-score.

**Machine Learning Models Implemented**

Logistic Regression:
GridSearchCV used
Minimal performance improvement

Random Forest Classifier:
GridSearchCV tuning
Accuracy improved from 0.692 → 0.693
Strong feature importance insights

XGBoost Classifier:
Hyperparameter tuning attempted
Performed well but not better than Random Forest

**Final Model Selection**
Random Forest Classifier selected as final model because:
Balanced performance across precision, recall, and F1-score
Handles imbalanced data effectively
Provides feature importance insights
Robust and less prone to overfitting

**Evaluation Metrics Considered**
Accuracy
Precision
Recall
F1-Score
Recall was particularly important to identify dissatisfied customers (low CSAT scores).

**Important Features Identified**

Top influential features:
Sub-category_Return Request
Channel Name (Inbound/Outcall)
Sub-category_Fraudulent User
Tenure Bucket (>90 days)
Agent Shift (Morning/Evening)
These factors significantly impact customer satisfaction.

**Technologies Used**

Programming Language:
Python

Libraries:
NumPy
Pandas
Matplotlib
Seaborn
Scikit-learn
imbalanced-learn (SMOTE)
XGBoost

**Key Business Impact** :
Early detection of dissatisfied customers
Improved customer retention
Better agent performance monitoring
Data-driven customer support optimization
Reduced churn risk

**Model Deployment Preparation** :
Saved best model using Pickle / Joblib
Reloaded model for sanity prediction check
Deployment-ready pipeline created

**Conclusion**

This project demonstrates how machine learning can be leveraged to predict Customer Satisfaction (CSAT) scores using customer support data.
By combining robust preprocessing, hypothesis testing, feature engineering, imbalance handling (SMOTE), and ensemble modeling, the final Random Forest model provides actionable insights for improving service quality.
The solution empowers businesses like Flipkart to proactively improve customer experience, optimize operations, and enhance long-term profitability.
