# Credit Approval/Disapproval Analysis using EDA

## Introduction
This project conducts an **Exploratory Data Analysis (EDA)** on loan application data to identify patterns and key factors influencing loan defaults. The analysis helps a consumer finance company make informed decisions to minimize financial losses while maximizing approvals for creditworthy applicants.

## Objective
- Identify driver variables that predict loan defaults.
- Analyze the impact of income, employment history, credit scores, and other factors on repayment capability.
- Provide actionable insights to optimize the loan approval process.

## Steps Conducted
1. **Data Cleaning**:
   - Removed columns with >50% missing values.
   - Imputed missing data (e.g., median for `AMT_GOODS_PRICE`, mode for `NAME_TYPE_SUITE`).
   - Converted negative days (e.g., `DAYS_BIRTH`, `DAYS_EMPLOYED`) to positive values.

2. **Outlier Detection**:
   - Flagged unrealistic values (e.g., income of 117M, 19 children).
   - Identified unemployed applicants (`DAYS_EMPLOYED = 365,243`).

3. **Feature Engineering**:
   - Binned `AMT_INCOME_TOTAL` into tiers (Low, Average, High).
   - Categorized `AMT_CREDIT` into risk-based buckets.

4. **Visualization & Analysis**:
   - Explored target class imbalance (92% non-default vs. 8% default).
   - Analyzed correlations (e.g., `AMT_CREDIT` vs. `AMT_GOODS_PRICE`).
   - Identified key risk factors (e.g., low `EXT_SOURCE_2` scores).

## Results
- **High-Risk Groups**:
  - Applicants with credit amounts >4x their annual income.
  - Unemployed individuals (outliers in `DAYS_EMPLOYED`).
  - Those with low external credit scores (`EXT_SOURCE_2 < 0.5`).
- **Key Insights**:
  - Strong correlation between credit amount and goods price (0.98).
  - Negative correlation between external scores and regional risk ratings (-0.29).

## Conclusion
The EDA highlights **income-credit mismatch**, **employment status**, and **external credit scores** as critical predictors of loan defaults. To mitigate risk, the company should:
1. Set stricter income-to-credit ratio thresholds.
2. Prioritize applicants with higher `EXT_SOURCE_2` scores.
3. Investigate outliers (e.g., unemployed applicants) for additional verification.

---

Feel free to explore the code, tweak the model, and visualize the results further. Contributions and feedback are welcome!

**Tools Used:**  
Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook  

**Author:** [Jay Thakur]
