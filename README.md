# Customer Churn & Retention Analytics

An end-to-end customer churn analysis project using Python, statistics, machine learning, and Excel reporting to identify churn patterns, predict customer risk, estimate revenue exposure, and support retention prioritization.

## Overview

This project analyzes **7,043 telecom customers from a US-based telecommunications dataset** to understand customer churn and identify where retention efforts can be prioritized.

The analysis covers:

- Customer and churn patterns
- Data cleaning and validation
- Exploratory data analysis
- Statistical testing
- Predictive modeling
- Customer-level churn probability
- Risk segmentation
- Customer value segmentation
- Expected monthly revenue risk
- Risk validation and model interpretation
- Excel-based reporting
- Retention recommendations

## Project Workflow

```text
Raw Customer Data
       ↓
Data Cleaning & Validation
       ↓
Feature Engineering
       ↓
Exploratory Data Analysis
       ↓
Statistical Analysis
       ↓
Predictive Modeling
       ↓
Model Evaluation & Comparison
       ↓
Churn Probability
       ↓
Risk Segmentation
       ↓
Customer Value Segmentation
       ↓
Revenue Risk Estimation
       ↓
Risk Validation & Model Interpretation
       ↓
Export Excel Report
       ↓
Retention Prioritization
       ↓
PowerPoint Presentation
```

## Tech Stack

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Scikit-learn
- Microsoft Excel
- Microsoft PowerPoint

## Project Files

- Telco-Customer-churn-Raw-Dataset.csv — [Click here to preview](https://drive.google.com/file/d/19PKvJRrOpzuQ4guPGAD6pwfJq-Sx7I4q/view?usp=drive_link)
- Python Notebook.ipynb — [Click here to preview](https://drive.google.com/file/d/1V9i3dgmHyhhOZRur1yB5vtJRy0M_jRqB/view?usp=drive_link)
- Excel Report — [Click here to preview](customer_churn_analysis.xlsx)
- PowerPoint Presentation — [Click here to preview](Customer_Churn_Analysis.pptx)
- [README.md](README.md) — Project documentation

## Project Structure

```text
Customer-Churn-Analytics/
│
├── Telco-Customer-churn-Raw-Dataset.csv
├── Python Notebook.ipynb
├── Excel Report.xlsx
├── PowerPoint Presentation.pptx
└── README.md
```

## Key Results

| Metric | Result |
|---|---:|
| Total Customers | 7,043 |
| Churned Customers | 1,869 |
| Overall Churn Rate | 26.54% |
| Average Tenure | 32.37 months |
| Average Monthly Charges | $64.76 |
| High-Risk Customers (>60%) | 990 |
| High-Risk Customer Share | 14.06% |
| Expected Monthly Revenue Risk | $139,938.75 |

## What I Analyzed

### Customer & Churn Analysis

- Overall churn rate
- Churn by contract type
- Churn by tenure group
- Churn by payment method
- Monthly charges and tenure patterns
- Customer characteristics associated with churn

### Statistical Analysis

Used statistical tests to evaluate relationships between churn and key variables:

- Welch's t-test for tenure
- Welch's t-test for monthly charges
- Chi-square test for contract type
- Cohen's d for effect size

The statistical tests showed significant relationships between churn and tenure, monthly charges, and contract type at `p < 0.001`.

## Machine Learning

Two classification models were developed and evaluated:

- Logistic Regression
- Random Forest

### Model Evaluation

The models were evaluated using a **single stratified train/test split**.

| Model | Accuracy | Precision | Recall | F1 | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 79.99% | 65.65% | 51.60% | 57.78% | 84.53% |
| Random Forest | 78.99% | 63.83% | 48.13% | 54.88% | 82.68% |

Among the two baseline models tested, **Logistic Regression achieved the higher ROC-AUC and F1-score**.

> **Modeling note:** No cross-validation, threshold tuning, or systematic hyperparameter tuning was performed. Logistic Regression used the default 0.5 classification threshold, while Random Forest used class weighting to address class imbalance. Therefore, this comparison should be viewed as a baseline model comparison rather than a fully optimized benchmark.

## Risk Segmentation

Each customer was assigned a predicted churn probability and classified into one of three risk segments:

- Low Risk
- Medium Risk
- High Risk

## Customer Value & Priority Segmentation

Customers were segmented using:

- **Value segment** based on monthly charges
- **Risk segment** based on predicted churn probability

This produced six priority groups:

- High Value / High Risk
- High Value / Medium Risk
- High Value / Low Risk
- Low Value / High Risk
- Low Value / Medium Risk
- Low Value / Low Risk

## Revenue Risk

Expected monthly revenue risk was estimated at the customer level using:

```text
Expected Monthly Revenue Risk = Monthly Charges × Churn Probability
```

Total estimated monthly revenue risk:

**$139,938.75**

This figure is a model-based estimate calculated from churn probabilities generated across the full analyzed customer dataset. It represents expected monthly revenue exposure associated with predicted churn risk, not confirmed revenue loss or an out-of-sample forecast.

## Key Findings

- Month-to-month customers had a **42.71% observed churn rate**, compared with **2.83%** for two-year contract customers.
- Customers with **0–6 months of tenure** had a **52.94% observed churn rate**.
- Electronic-check customers had a **45.29% observed churn rate**.
- Churned customers had lower average tenure and higher average monthly charges than retained customers.
- Fiber-optic service had a **3.47× modeled odds ratio for churn** relative to the reference category, holding other modeled variables constant.
- Two-year contracts had a **0.23× modeled odds ratio** relative to the reference contract category.


## Excel Report

The final Excel report was created to organize the main analytical outputs into business-friendly tables.

The workbook contains:

- **Customer Data** — customer-level analysis data
- **KPIs** — overall business and churn KPIs
- **Priority Segments** — customer value and risk segmentation
- **Risk Validation** — actual churn vs. predicted risk by segment
- **Model Comparison** — Logistic Regression and Random Forest metrics
- **Feature Importance** — Random Forest feature importance
- **Logistic Coefficients** — modeled coefficients and odds ratios
- **Risk Deciles** — predicted risk vs. actual churn across deciles
- **Priority Customers** — customer-level retention prioritization list

**Note:** Risk scores, risk segments, risk deciles, and expected revenue risk in the report were generated by applying the trained model to the full analyzed customer dataset. The held-out test set was used separately for model performance evaluation.

## Retention Recommendations

Based on the analysis:

1. **Prioritize high-value, high-risk customers** because this segment combines higher customer value with elevated predicted churn risk.

2. **Focus retention analysis on contract type**, as observed churn varies substantially across contract lengths.

3. **Investigate the fiber-optic churn association** to understand whether pricing, service quality, or support experience may contribute to the observed relationship.

4. **Evaluate payment-method migration**, particularly whether moving electronic-check customers toward automatic payment methods can reduce churn.

5. **Use customer-level churn probabilities** to prioritize retention activity instead of treating all customers equally.


## Key Takeaway

This project combines descriptive analytics, statistical analysis, predictive modeling, risk segmentation, and business reporting to move from:

**"Who has churned?"**

to:

**"Who is at risk, how much revenue is associated with that risk, and where should retention efforts be prioritized?"**

> Note: Churn relationships and odds ratios describe statistical/model associations and should not be interpreted as proof of causation. Model performance was evaluated on a held-out test set, while customer-level risk and revenue-risk estimates were generated across the full analyzed customer dataset.
