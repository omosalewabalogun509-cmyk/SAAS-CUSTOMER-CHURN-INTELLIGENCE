# SAAS CUSTOMER CHURN INTELLIGENCE

## Project Overview

Customer churn is a major challenge for Software-as-a-Service (SaaS) businesses because losing customers can affect revenue, business growth, and long-term customer relationships.

This project uses Python to analyse customer churn patterns in a SaaS dataset containing 50,000 records. The analysis focuses on identifying the characteristics of churned customers across industries, subscription plan tiers, payment statuses, countries, account managers, and customer activity dates.

The goal is to generate insights that can help businesses understand customer churn and develop better customer retention strategies.

## Project Objectives

- Analyse the distribution of churned and non-churned customers.
- Identify the industries with the highest numbers of churned customers.
- Examine churn across subscription plan tiers.
- Analyse payment status among churned customers.
- Explore churned customer counts across different countries.
- Examine churn patterns by account manager.
- Identify the years and months associated with customers' last activity.
- Recommend strategies for improving customer retention.

## Tools and Technologies

- **Python:** Programming language used for data analysis.
- **Jupyter Notebook:** Environment used to perform and document the analysis.
- **Pandas:** Used for data cleaning, manipulation, grouping, and summarisation.
- **Matplotlib:** Used for data visualisation.
- **Seaborn:** Used to create statistical charts and visualise customer churn patterns.

## Dataset Description

The dataset contains 50,000 records and includes customer information used to explore churn patterns.

Key columns analysed include:

- `company_name`
- `industry`
- `plan_tier`
- `payment_status`
- `feature_adoption_rate`
- `country`
- `account_manager`
- `signup_date`
- `last_active_date`
- `is_churned`

The `is_churned` column identifies whether a customer has churned. In this project, `1` is converted to `churned`, while `0` is converted to `not_churned`.

## Project Workflow

### 1. Data Loading

The dataset was imported into Python using Pandas.

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("MP_Synthetics_50000_Rows.csv")
```

### 2. Data Cleaning

The column names were converted to lowercase, and extra spaces were removed to improve consistency.

Duplicate records and missing values were also checked.

```python
df.columns = df.columns.str.lower()
df.columns = df.columns.str.strip()

df.duplicated().sum()
df.isna().sum()
```

### 3. Data Inspection

The dataset was examined to understand its structure, dimensions, data types, and summary statistics.

```python
df.shape
df.head()
df.info()
df.describe().T
df.nunique()
```

### 4. Date Conversion

The signup and last activity columns were converted to datetime format to support date-based analysis.

```python
df["signup_date"] = pd.to_datetime(df["signup_date"])
df["last_active_date"] = pd.to_datetime(df["last_active_date"])
```

### 5. Churn Identification

The churn indicator was converted into readable categories, and churned customers were separated for further analysis.

```python
df["is_churned"] = df["is_churned"].replace({
    1: "churned",
    0: "not_churned"
})

churned_data = df[df["is_churned"] == "churned"]
```

### 6. Exploratory Data Analysis

The churned customer dataset was grouped by industry, plan tier, payment status, country, and account manager.

Bar charts and a line chart were used to explore customer counts and activity-date patterns.

## Key Findings

### 1. Customer Churn by Industry

EdTech recorded the highest churn count among the five highlighted industries, with 128 customers. DevTools followed with 121, Logistics with 119, MarTech with 113, and CyberSecurity with 112.

**Insight:** EdTech may be a useful starting point for investigating customer retention challenges. However, churn rates are needed to determine which industry loses the greatest proportion of its customers.

### 2. Customer Churn by Subscription Plan

The Starter plan recorded 685 churned customers, followed by Pro with 174 and Enterprise with 57.

**Insight:** The Starter plan accounts for the largest number of churned customers in the analysis. The business should investigate onboarding, customer engagement, support, pricing, and perceived plan value.

### 3. Customer Churn by Country

Among the countries reported, Singapore had the highest churned customer count at 135, followed by the USA with 126 and France with 125. The UK had the lowest count at 95.

**Insight:** These results identify differences in churned customer counts across countries. Segment-level churn rates are needed before concluding that any country has a higher risk of churn.

### 4. Payment Status Analysis

Payment status was examined among churned customers to explore possible relationships between payment conditions and customer departures.

**Insight:** Payment status may help identify potential retention issues. Further analysis is required to establish whether particular payment statuses are associated with higher churn rates.

### 5. Account Manager Analysis

Churned customers were grouped by account manager to compare the number of customers associated with each manager.

**Insight:** This analysis can help identify areas for further investigation into customer support and account management. Customer portfolios and total customers managed must be considered before comparing performance.

### 6. Customer Activity Over Time

The year and month were extracted from `last_active_date` to examine when churned customers were last active.

**Insight:** Date-based analysis can help identify possible periods of reduced customer activity. Further analysis is needed to distinguish seasonal patterns from changes in the customer base.

## Business Recommendations

1. **Improve the Starter plan experience:** Investigate why the Starter plan has the largest churn count and consider improving onboarding, support, engagement, and feature value.

2. **Investigate industry-specific challenges:** Examine the needs and expectations of EdTech customers to identify possible reasons for churn.

3. **Review payment-related issues:** Investigate failed payments, billing difficulties, and other payment-status patterns where supported by the data.

4. **Strengthen customer engagement:** Monitor feature adoption and last activity dates to identify customers who may need additional support.

5. **Evaluate account management:** Compare churn rates across account managers while accounting for portfolio size and customer characteristics.

6. **Calculate segment-level churn rates:** Compare churned customers with the total number of customers in each industry, country, and subscription plan.

## Limitations and Further Analysis

This project primarily examines the number of churned customers in different groups. Customer counts alone do not establish which groups have the highest likelihood of churn because group sizes may differ.

Further analysis should include:

- Churn rates by industry, country, and subscription plan.
- Comparisons between churned and non-churned customers.
- Investigation of feature adoption and payment status.
- Analysis of customer tenure and time since last activity.
- Validation of data quality and relationships before making business decisions.

## Conclusion

The SaaS Customer Churn Intelligence project demonstrates how Python and exploratory data analysis can be used to investigate customer churn patterns.

The findings highlight the Starter subscription plan and EdTech industry as useful starting points for further investigation. Country, payment status, account manager, and activity-date analyses provide additional areas to explore.

By calculating segment-level churn rates and investigating customer behaviour, SaaS businesses can make more informed decisions, improve customer engagement, and develop more effective retention strategies.

## Author

**Balogun Omosalewa Victoria**

- **Phone:** 09039085488
- **Email:** omosalewabalogun509@gmail.com

---

*This project was completed using Python, Pandas, Matplotlib, Seaborn, and Jupyter Notebook.*
