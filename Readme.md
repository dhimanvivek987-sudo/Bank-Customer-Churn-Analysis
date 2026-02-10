# Bank Customer Churn Analysis  
## A Data-Driven, Explainable Analytics Case Study

---

## Executive Summary

Customer churn is a critical challenge in the banking industry. While predictive models can identify customers at risk, business teams often struggle to understand **why** customers churn and **how** to intervene effectively.

This project analyzes bank customer churn using data analytics and explainable machine learning. The focus is not only on predicting churn, but on **quantifying key drivers**, explaining individual predictions, and translating insights into **actionable retention strategies**.

---

## Business Problem

Banks incur significant revenue and relationship losses when customers churn. These decisions are rarely random and are typically influenced by pricing, engagement, service usage, and relationship length.

This analysis addresses the following business questions:

1. Which customers are most likely to churn?
2. What factors increase or reduce churn risk?
3. How can churn insights inform targeted retention strategies?

---

## Dataset Source

The dataset used in this project is the **Bank Customer Churn Modeling** dataset, publicly available on Kaggle:

**Dataset link:**  
https://www.kaggle.com/datasets/shrutimechlearn/churn-modelling

This dataset is widely used for banking churn analysis and customer behavior modeling.

---

## Dataset Overview (Before Cleaning)

- **Total records:** 10,000 customers  
- **Total columns:** 14  
- **Target variable:** `Exited`  
  - 1 → Customer churned  
  - 0 → Customer retained  

### Feature Categories
- Customer demographics (Geography, Gender)
- Relationship and tenure information
- Financial indicators (Balance, Salary)
- Product and service usage

---

## Data Cleaning and Preparation

Data cleaning was performed using business logic and data integrity checks.

### 1. Removal of Non-Informative Identifiers
The following columns were removed as they do not contribute to churn prediction:
- RowNumber
- CustomerId
- Surname

**Records removed:** 0  
**Records remaining:** 10,000

---

### 2. Data Type Validation
- All numerical columns were validated and cast to numeric types.
- No invalid or corrupted numeric values were found.

---

### 3. Missing Value Analysis
- The dataset contains **no missing values**.
- No imputation or record removal was required.

**Records removed:** 0  
**Records remaining:** 10,000

---

### 4. Categorical Encoding
Categorical variables such as:
- Geography
- Gender

were encoded into numerical representations suitable for machine learning while preserving business meaning.

---

## Dataset Summary (After Cleaning)

| Stage | Number of Records |
|-----|------------------|
| Raw dataset | 10,000 |
| After cleaning | 10,000 |

No customer records were dropped during the cleaning process.

---

## Target Variable Distribution

- **Churned customers:** ~2,000  
- **Retained customers:** ~8,000  

This imbalance reflects real-world banking behavior, where the majority of customers remain with the bank.

---

## Exploratory Data Analysis

Exploratory analysis was conducted to understand behavioral differences between churned and retained customers.

### Key Observations
- Customers with higher financial exposure show higher churn tendency.
- Longer-tenure customers are more stable.
- Service adoption patterns differ clearly across churn groups.

These patterns guided feature selection and modeling decisions.

---

## Modeling and Explainability

A machine learning model was trained to estimate **individual churn probability**.

Model outputs range from **0 to 1**, where:
- 0 indicates low churn risk
- 1 indicates high churn risk

To ensure transparency, **SHAP (SHapley Additive Explanations)** was used to interpret predictions and quantify feature-level contributions.

---

## Example Model Output (With Numbers)

For a representative customer, the model produced a **churn probability of 0.42**, indicating moderate churn risk.

### Factors Increasing Churn Risk
- Higher monthly financial exposure
- Short-term relationship indicators
- Electronic payment and billing behavior

### Factors Reducing Churn Risk
- Higher cumulative customer value (total charges)
- Adoption of security and support services

The final probability (0.42) reflects the combined effect of multiple contributing factors.

## Dataset Source

The dataset used in this project is the **Bank Customer Churn Modeling** dataset, publicly available on Kaggle:

https://www.kaggle.com/datasets/shrutimechlearn/churn-modelling

The dataset contains **10,000 customer records** from a retail banking context and is widely used for churn analysis and customer behavior modeling.

---

## Dataset Structure (Before Cleaning)

- **Total records:** 10,000 customers  
- **Total columns:** 14  
- **Target variable:** `Exited`  
  - 1 → Customer churned  
  - 0 → Customer retained  

### Feature Categories
- Customer demographics (e.g., Geography, Gender)
- Account and relationship information
- Financial indicators
- Product and service usage

---

## Data Cleaning and Preparation

Data cleaning was performed to ensure analytical accuracy and business relevance.

### 1. Removal of Non-Informative Identifiers
The following columns were removed as they do not contribute to churn prediction:
- RowNumber
- CustomerId
- Surname

**Records removed:** 0  
**Remaining records:** 10,000

---

### 2. Data Type Validation
- All numerical columns were verified and cast to appropriate numeric types.
- No corrupted or invalid numeric values were found.

---

### 3. Missing Value Analysis
- The dataset contains **no missing values**.
- No imputation was required.

**Records removed:** 0  
**Remaining records:** 10,000

---

### 4. Categorical Encoding
Categorical variables such as:
- Geography
- Gender

were encoded into numerical format to support machine learning modeling.

---

## Dataset After Cleaning

| Stage | Number of Records |
|----|-----------------|
| Raw dataset | 10,000 |
| After cleaning | **10,000** |

No records were dropped during cleaning, ensuring full data retention.

---

## Target Variable Distribution

- **Churned customers:** ~2,000  
- **Retained customers:** ~8,000  

This imbalance reflects real-world banking behavior, where most customers do not churn.

---

## Feature Set Used for Modeling

After preprocessing, the model used:
- **10 predictive features**
- 1 binary target variable (`Exited`)

Key features include:
- Credit Score
- Geography
- Age
- Tenure
- Balance
- Number of Products
- Has Credit Card
- Is Active Member
- Estimated Salary
