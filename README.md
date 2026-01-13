# python-eda-loan-project
# Loan Default Risk Analysis (EDA)

## Project Overview
This project performs **Exploratory Data Analysis (EDA)** on a real-world loan application dataset to identify patterns and risk factors associated with **loan default**.

This work was completed as part of an **internship assignment**.

---

## Problem Statement
Financial institutions face two major risks:
1. Rejecting applicants who are capable of repaying loans (loss of business).
2. Approving applicants who later default (financial loss).

The objective of this analysis is to analyze applicant and loan data to identify key drivers of default risk.

---

## Datasets Used
- **application_data.csv**  
  Contains applicant-level information at the time of loan application.

- **previous_application.csv**  
  Contains historical loan application details of clients.

- **columns_description.csv**  
  Data dictionary explaining the meaning of each column.

**Target Variable**
- `TARGET = 0` → No payment difficulty  
- `TARGET = 1` → Payment difficulty (default)

---

## Key Steps Performed

### 1. Data Understanding
- Explored dataset structure, feature types, and target variable.

### 2. Missing Data Analysis
- Dropped columns with >40% missing values.  
- Applied median imputation for selected numeric features.  
- Handled anomaly values (e.g., `DAYS_EMPLOYED = 365243`).


### 3. Outlier Detection
- Used the **IQR (Interquartile Range) method** to identify outliers in key numerical variables.
- Visualized outliers using boxplots.
- Outliers were retained for analysis, as they may represent genuine high-value clients.

### 4. Target Imbalance Analysis
- Identified strong class imbalance:
  - 0 (No default): 282,686 (~91.95%)
  - 1 (Default): 24,825 (~8.05%)
- Imbalance ratio ≈ **11.4 : 1**
- Visualized imbalance using bar plots.

### 5. Univariate Analysis
- Analyzed distributions of numerical and categorical variables.
- Identified skewness, dominant categories, and potential outliers in the data.

### 6.Segmented Analysis by TARGET 
- Key numerical features were analyzed separately for defaulters and non-defaulters.
- Highlighted how borrower characteristics such as income, credit amount, and age differ between the two groups.

### 7. Bivariate Analysis
- Explored relationships between feature pairs and their link to default risk.  
Two key variable pairs were analyzed:  
- **Income vs Credit:** High credit relative to income increases default risk.  
- **Employment vs Previous Applications:** Longer employment lowers risk, while multiple past refusals increase it.

### 8. Correlation Analysis
- Computed correlations separately for defaulters and non-defaulters.
- Identified top correlated numeric feature pairs (excluding TARGET).
- Observed more variability in correlations for defaulting clients.

---

## Key Insights
- Loan default risk increases with **lower income**, **higher credit-to-income ratios**, and **younger age**.
- Applicants with **multiple past refusals** show a higher likelihood of default.
- Stable employment and past approvals are associated with lower risk.
- Defaults are rare but costly, requiring imbalance-aware analysis.

---

## Tools & Technologies
- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Jupyter Notebook / VS Code  

---

## Conclusion
This EDA highlights critical drivers of loan default and provides actionable insights for credit risk assessment.  
The findings can help financial institutions reduce default risk while avoiding unnecessary rejection of reliable customers.

---

## Author
**Arfa Tazmeen**  
Internship Project
