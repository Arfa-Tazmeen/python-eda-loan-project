# python-eda-loan-project
# Loan Default Risk Analysis (EDA)

## Project Overview
This project performs **Exploratory Data Analysis (EDA)** on a real-world loan application dataset to identify patterns and risk factors associated with **loan default**.  
The analysis helps understand customer behavior and supports better credit risk decision-making.

This work was completed as part of an **internship assignment**.

---

## Problem Statement
Financial institutions face two major risks:
1. Rejecting applicants who are capable of repaying loans (loss of business).
2. Approving applicants who later default (financial loss).

The objective of this analysis is to explore customer and loan attributes to identify factors that differentiate **clients with payment difficulties** from others.

---

## Datasets Used
- **application_data.csv**  
  Contains applicant-level information at the time of loan application.

- **previous_application.csv**  
  Contains historical loan application details of clients.

- **columns_description.csv**  
  Data dictionary explaining the meaning of each column.

**Target Variable**
- `TARGET = 0` → No payment difficulties  
- `TARGET = 1` → Payment difficulties (default)

---

## Key Steps Performed

### 1. Data Understanding
- Inspected dataset structure, size, and column definitions.
- Identified numerical and categorical features.

### 2. Missing Data Analysis
- Calculated missing value counts and percentages for all columns.
- Dropped columns with more than **40% missing values**.
- Applied **median imputation** for selected numerical variables (e.g., `AMT_ANNUITY`).
- Handled special anomaly values (e.g., `DAYS_EMPLOYED = 365243`) by flagging and replacing with NaN.

### 3. Outlier Detection
- Used the **IQR (Interquartile Range) method** to identify outliers in key numerical variables.
- Visualized outliers using boxplots.
- Outliers were not removed, as they may represent genuine high-value clients.

### 4. Target Imbalance Analysis
- Identified strong class imbalance:
  - 0 (No default): 282,686 (~91.95%)
  - 1 (Default): 24,825 (~8.05%)
- Imbalance ratio ≈ **11.4 : 1**
- Visualized imbalance using bar plots with counts and percentages.

### 5. Univariate & Segmented Analysis
- Analyzed distributions of numerical and categorical variables.
- Compared feature distributions across default and non-default clients.
- Observed higher default risk among:
  - Lower-income applicants
  - Younger applicants
  - Higher loan-to-income ratios

### 6. Previous Application Feature Engineering
- Aggregated historical loan data per client:
  - Number of previous applications
  - Number of approvals and refusals
  - Mean and maximum previous credit amounts
- Merged engineered features with main application data.
- Found that repeated past refusals are linked to higher default risk.

### 7. Correlation Analysis
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
