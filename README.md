# 📊 Credit Risk & Loan Portfolio Analytics

<p align="center">
  <img src="Dashboard/Executive_Overview.png" alt="Executive Overview" width="900"/>
</p>

## 📌 Project Overview

The **Credit Risk & Loan Portfolio Analytics Dashboard** is an end-to-end Power BI project designed to analyze loan portfolio exposure, credit risk, defaults, expected losses, and capital requirements.

The dashboard transforms raw loan-level data into interactive financial risk insights that can help banking and lending teams monitor portfolio quality, identify high-risk segments, and understand exposure concentration.

---

## 🎯 Business Objectives

This project focuses on answering key credit-risk questions:

- Where is the loan portfolio exposure concentrated?
- Which sectors have higher high-risk exposure?
- Where is defaulted exposure concentrated?
- Which loan types have higher default rates?
- How does credit rating relate to expected loss?
- What proportion of the portfolio is exposed to high-risk loans?
- How does credit score distribution vary across the portfolio?
- What is the portfolio's expected loss and risk-weighted exposure?

---

## 📊 Key Portfolio Metrics

| Metric | Value |
|---|---:|
| Total Loans | 50K+ |
| Total EAD | 164.93 Bn |
| Default Rate | 13.90% |
| Expected Loss | 1.92 Bn |
| RWA | 25.49 Bn |
| High-Risk Exposure | 8.72% |

> **EAD:** Exposure at Default  
> **RWA:** Risk-Weighted Assets  
> **PD:** Probability of Default  
> **LGD:** Loss Given Default

---

## 🛠️ Tools & Technologies

- **Power BI**
- **Power Query**
- **DAX**
- **Data Modeling**
- **Data Cleaning & Transformation**
- **Financial Analytics**
- **Credit Risk Analysis**
- **Data Visualization**

---

## 🗂️ Dataset

The project uses multiple datasets covering loan-level portfolio information and supporting risk analysis.

### Main Data

- `loan_portfolio.csv`
- `credit_ratings.csv`
- `macro_stress_scenarios.csv`
- `portfolio_metrics.csv`
- `vintage_analysis.csv`

The loan portfolio contains information such as:

- Loan ID
- Origination Date
- Maturity Date
- Sector
- Loan Type
- Collateral
- Credit Rating
- Credit Score
- EAD
- Coupon Rate
- Leverage
- Interest Coverage
- Debt-to-Equity
- PD
- LGD
- Expected Loss
- Unexpected Loss
- RWA
- Default Status
- Recovery Rate

---

## 🧹 Data Preparation

Data preparation was performed using **Power Query** and included:

- Data type validation
- Missing-value handling
- Duplicate checks
- Date transformation
- Column standardization
- Data quality validation
- Creation of analytical dimensions

Expected null values in fields such as `default_date`, `recovery_rate`, and `loss_given_default` were retained for non-defaulted loans where appropriate.

---

## 🧩 Data Modeling

A structured dimensional model was created in Power BI to support efficient filtering and analysis.

### Dimension Tables

- DateTable
- DimSector
- DimVintage
- DimLoanType
- DimCollateral
- DimRating

### Fact / Analytical Tables

- loan_portfolio
- credit_ratings
- portfolio_metrics
- vintage_analysis
- macro_stress_scenarios

<p align="center">
  <img src="Documentation/data_model.png" alt="Power BI Data Model" width="900"/>
</p>

The model uses appropriate **one-to-many relationships** and **single-direction filtering** for consistent analytical behavior.

---

## 🧮 DAX Analysis

Key DAX measures and calculated columns include:

### Portfolio KPIs

- Total Loans
- Total EAD
- Defaulted Loans
- Default Rate
- Total Expected Loss
- Total RWA
- Total Unexpected Loss

### Credit Risk Metrics

- Average PD
- Average LGD
- Average Credit Score
- High Risk Loans
- High Risk EAD
- High Risk Exposure %
- Defaulted EAD
- Defaulted EAD %
- Expected Loss Rate
- RWA to EAD %

### Risk Classification

Loans were categorized using annual Probability of Default:

- **High Risk:** PD ≥ 10%
- **Medium Risk:** PD ≥ 5% and < 10%
- **Low Risk:** PD < 5%

Additional analytical columns include:

- Vintage
- Credit Score Band
- Risk Category

Detailed DAX formulas are available in:

`DAX/DAX_Measures.md`

---

## 📈 Dashboard Pages

### 1️⃣ Executive Overview

The Executive Overview provides a high-level view of the overall loan portfolio.

Key visuals include:

- Total Loans
- Total EAD
- Default Rate
- Expected Loss
- RWA
- Loan Exposure by Sector
- Default Rate by Credit Rating
- Loan Exposure by Loan Type
- Loan Distribution by Risk Category

<p align="center">
  <img src="Dashboard/Executive_Overview.png" alt="Executive Overview Dashboard" width="900"/>
</p>

---

### 2️⃣ Credit Risk Deep Dive

The Credit Risk Deep Dive focuses on portfolio risk concentration and default exposure.

Key analysis includes:

- High Risk Loans
- High Risk EAD
- High Risk Exposure %
- Defaulted EAD %
- Expected Loss Rate
- High Risk Exposure by Sector
- Default Rate by Loan Type
- Expected Loss by Credit Rating
- Credit Score Distribution
- Defaulted Exposure by Sector

<p align="center">
  <img src="Dashboard/Credit_Risk_Deep_Dive.png" alt="Credit Risk Deep Dive Dashboard" width="900"/>
</p>

---

## 💡 Key Business Insights

The analysis highlights several portfolio-level patterns:

- High-risk exposure is concentrated across major sectors including Real Estate and Financials.
- Defaulted exposure is concentrated in selected sectors, indicating areas requiring closer portfolio monitoring.
- Loan types show differences in default rates.
- Expected loss is more concentrated among lower credit-rating segments.
- Credit score distribution provides additional visibility into borrower risk quality.
- Portfolio-level exposure, expected loss and RWA provide a combined view of credit risk and capital requirements.

---

## 📁 Repository Structure

```text
credit-risk-loan-portfolio-analytics/
│
├── Dashboard/
│   ├── Credit Risk & Loan Analysis.pbix
│   ├── Executive_Overview.png
│   └── Credit_Risk_Deep_Dive.png
│
├── Data/
│   ├── credit_ratings.csv
│   ├── loan_portfolio.csv
│   ├── macro_stress_scenarios.csv
│   ├── portfolio_metrics.csv
│   └── vintage_analysis.csv
│
├── Documentation/
│   ├── data_model.png
│   └── credit_risk_column_descriptions.txt
│
├── DAX/
│   └── DAX_Measures.md
│
└── README.md
