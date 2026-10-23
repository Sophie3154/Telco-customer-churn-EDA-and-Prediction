# Telco Customer Churn Analysis & Prediction

## Project Overview

Customer churn is a major challenge for telecommunications companies, as retaining existing customers is essential for long-term business performance.

The goal of this project is to analyze customer churn patterns, identify customer characteristics associated with higher churn rates, and build machine learning models to predict which customers are more likely to leave the company.

The project combines exploratory data analysis, classification modeling, model evaluation, and business recommendations.

## Objectives

- Identify customer characteristics associated with churn.
- Explore relationships between customer behavior, services, contracts, and churn rates.
- Build and compare machine learning classification models.
- Evaluate model performance using appropriate metrics.
- Provide actionable recommendations to support customer retention strategies.

## Dataset

The project uses the Telco Customer Churn dataset, which contains customer information such as:

- **Demographics:** gender, senior citizen status, partner, and dependents.
- **Services:** internet service, online security, technical support, streaming services, and more.
- **Account information:** contract type, tenure, monthly charges, and total charges.
- **Target variable:** whether the customer churned (`Yes` or `No`).

The `customerID` column was excluded from the predictive features because it is an identifier rather than a meaningful customer characteristic.

## Tools & Technologies

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- XGBoost
- Jupyter Notebook

## Methodology

### 1. Data Cleaning and Preparation

- Inspected the dataset and handled missing or invalid values.
- Converted variables to appropriate data types.
- Encoded categorical variables for machine learning.
- Separated features from the target variable.
- Split the data into training and testing sets.

### 2. Exploratory Data Analysis (EDA)

Analyzed churn rates across customer characteristics, including:

- Contract type
- Customer tenure
- Monthly charges
- Online security
- Technical support

### 3. Machine Learning Models

Three classification models were trained and evaluated:

- Logistic Regression
- Random Forest
- XGBoost

Grid search with cross-validation was used to tune the hyperparameters of the Random Forest and XGBoost models.

### 4. Model Evaluation

The models were compared using:

- **Recall:** the proportion of actual churners correctly identified.
- **Precision:** the proportion of customers predicted to churn who actually churned.
- **F1-score:** the balance between precision and recall.
- **Accuracy:** the proportion of all predictions that were correct.

Recall was prioritized during hyperparameter selection because identifying customers likely to churn was the main objective.

## Key Findings

The exploratory analysis revealed several patterns:

- Customers with month-to-month contracts had substantially higher churn rates than customers with longer-term contracts.
- Customers with shorter tenure were more likely to churn.
- Customers with higher monthly charges tended to have higher churn rates.
- Customers without online security or technical support had higher churn rates than customers subscribed to these services.

These findings highlight customer groups that may deserve further investigation as part of a retention strategy.

## Model Results

The Logistic Regression model achieved the best recall and F1-score among the three models evaluated.

| Model | F1-score | Recall | Precision | Accuracy |
|---|---:|---:|---:|---:|
| Logistic Regression | 0.580 | 0.522 | 0.651 | 0.799 |
| Random Forest | 0.562 | 0.495 | 0.651 | 0.796 |
| XGBoost | 0.568 | 0.495 | 0.666 | 0.800 |

Logistic Regression was selected as the preferred model for the churn detection objective.

Its recall of 52.2% means that it correctly identified approximately 52% of customers who actually churned in the test set. Its precision of 65.1% means that approximately 65% of customers predicted to churn did so in the test set.

Although XGBoost achieved slightly higher precision and accuracy, Logistic Regression provided the best balance of precision and recall according to the F1-score.

## Business Recommendations

Based on the findings, the following actions could be explored:

- Monitor customers with month-to-month contracts more closely, especially those with short tenure.
- Test targeted offers for online security and technical support services.
- Develop retention campaigns for customers identified as having a high predicted churn risk.
- Conduct customer surveys to better understand dissatisfaction, customer needs, and potential areas for service improvement.

These recommendations should be tested to determine whether they lead to measurable reductions in churn.

## Limitations and Next Steps

The models do not identify the causes of churn, and the observed relationships should not be interpreted as causal.

Potential next steps include:

- Testing different classification thresholds to improve recall while maintaining acceptable precision.
- Evaluating model performance on new data.
- Measuring the effectiveness and cost of retention campaigns.
- Investigating customer feedback to better understand the reasons behind churn.

## Conclusion

This project demonstrates how exploratory data analysis and machine learning can help identify customer groups associated with higher churn risk.

Among the three models evaluated, Logistic Regression was the most suitable for the project's objective of identifying customers likely to churn. The results provide a starting point for targeted retention strategies, while further validation and business testing would be needed before practical deployment.
