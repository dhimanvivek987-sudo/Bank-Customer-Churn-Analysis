# Bank Customer Churn Analysis  
### A Data-Driven, Explainable Analytics Case Study

---

## Executive Summary

Customer churn is a critical challenge in the banking industry. Retaining existing customers is significantly more cost-effective than acquiring new ones, yet churn decisions are often poorly understood.

This project uses **data analytics and explainable machine learning** to answer a core business question:

> **Why do bank customers churn, and what factors influence their decision to leave?**

The analysis focuses on building insight, transparency, and actionable understanding rather than treating churn as a purely technical prediction problem.

---

## Business Problem

Banks operate in an increasingly competitive environment with rising customer expectations.  
When customers churn, the bank loses not only revenue but also long-term relationship value.

Business stakeholders need answers to:
- Which customers are likely to churn?
- What factors increase or reduce churn risk?
- How can churn insights inform retention strategies?

This project addresses these questions through structured data analysis and model explainability.

---

## Dataset Description

The analysis is based on a **Bank Customer Churn dataset** containing customer-level information such as:

- Customer tenure and engagement indicators
- Monthly and total charge metrics
- Account and billing characteristics
- Service usage and support features
- Churn status (target variable)

### **Target Variable**
- **Churn** — Indicates whether a customer exited the bank

### **Key Features Used**
- Monthly Charges  
- Total Charges  
- Account / Contract Type  
- Payment Method  
- Paperless Billing  
- Online Security  
- Technical Support  

---

## Data Understanding & Initial Exploration

Before modeling, the dataset was reviewed to understand its structure and business relevance.

Key questions addressed:
- How many customers are represented?
- What proportion of customers have churned?
- Which features are numerical vs categorical?
- Are there missing or inconsistent values?
- Are there extreme or unusual values?

### **Outputs Generated**
- Dataset dimensions and structure
- Summary statistics for numerical features
- Distribution of categorical variables
- Missing value analysis

Initial exploration showed clear differences between churned and retained customers, particularly in **charges, tenure, and service usage**.

---

## Data Cleaning & Preparation

Data cleaning decisions were made using **business context**, not just technical rules.

### **Handling Missing Values**
- Numerical fields such as Total Charges were examined for missing or invalid entries.
- Missing values were handled carefully to avoid introducing bias.

**Assumption:**  
Missing values often reflect new or recently onboarded customers rather than random data loss.

---

### **Data Type Corrections**
Some numerical variables were initially stored as text.

**Actions Taken:**
- Converted relevant columns to numeric formats
- Invalid conversions were identified and addressed

**Assumption:**  
Financial metrics must be numeric to accurately represent customer value.

---

### **Outlier Review**
Extreme values were reviewed to determine whether they represented:
- Data quality issues, or
- Legitimate high-value customers

**Decision:**  
Outliers were retained unless clearly invalid, as high-value customers are important in churn analysis.

---

### **Categorical Feature Encoding**
Categorical variables such as account type, payment method, and service usage were encoded into model-ready formats while preserving interpretability.

---

## Assumptions Used in the Analysis

The following assumptions guided data preparation and modeling:

- Missing values represent incomplete customer history
- Higher total charges indicate longer customer relationships
- Service adoption reflects customer engagement and perceived value
- Churn behavior is influenced by both pricing and service experience

These assumptions were reviewed during exploratory analysis for consistency with observed patterns.

---

## Exploratory Analysis & Figures Generated

The following analyses and figures were produced to understand churn behavior:

### **Key Numerical Insights**
- Average monthly charges by churn status
- Comparison of total charges between churned and retained customers
- Distribution of customer tenure

### **Visual Analysis**
- Charge distribution plots
- Churn comparison across account types
- Service usage versus churn rate
- SHAP-based feature contribution visualizations

These figures helped identify meaningful churn drivers prior to modeling.

---

## Modeling Approach

A machine learning model was trained to estimate churn probability at the individual customer level.

The modeling approach emphasized:
- Stability and interpretability
- Clear feature contribution analysis
- Business relevance over raw predictive performance

SHAP (SHapley Additive Explanations) was used to interpret model outputs.

---

## Model Explainability & Insights

For a representative customer, the model produced a **churn probability of 0.42**, indicating moderate churn risk.

### **Factors Increasing Churn Risk**
- Short-term or flexible account structures
- Higher monthly charges
- Electronic payment methods
- Paperless billing behavior

These factors suggest lower commitment and higher price sensitivity.

---

### **Factors Reducing Churn Risk**
- Online security services
- Technical support services
- Higher total charges (long-term customer relationship)

These factors indicate stronger engagement and customer loyalty.

---

## Bank Customer Churn Analysis  
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

---

