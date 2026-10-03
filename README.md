# 📊 Credit Risk & Loan Portfolio Analytics

<p align="center">
  <img src="Dashboard/Executive_Overview.png" alt="Credit Risk & Loan Portfolio Analytics" width="100%">
</p>

<p align="center">
  <strong>End-to-End Credit Risk & Loan Portfolio Analytics Dashboard using Power BI</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black">
  <img src="https://img.shields.io/badge/Power%20Query-742774?style=for-the-badge&logo=microsoft&logoColor=white">
  <img src="https://img.shields.io/badge/DAX-512BD4?style=for-the-badge&logo=microsoft&logoColor=white">
  <img src="https://img.shields.io/badge/Data%20Modeling-5B2C6F?style=for-the-badge&logo=databricks&logoColor=white">
  <img src="https://img.shields.io/badge/Financial%20Analytics-1F4E79?style=for-the-badge&logo=googleanalytics&logoColor=white">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Domain-Credit%20Risk-5B2C6F?style=flat-square">
  <img src="https://img.shields.io/badge/Analysis-Portfolio%20Risk-374151?style=flat-square">
  <img src="https://img.shields.io/badge/Status-Completed-success?style=flat-square">
</p>

---

## 📌 Project Overview

The **Credit Risk & Loan Portfolio Analytics Dashboard** is an end-to-end Power BI project designed to analyze loan portfolio exposure, credit risk, defaults, expected losses, and risk-weighted assets.

The project transforms loan-level financial data into an interactive business intelligence solution that helps analyze:

- Portfolio exposure
- Credit risk concentration
- Default patterns
- Expected credit losses
- Risk-weighted exposure
- Credit rating distribution
- Borrower credit quality
- Sector and loan-type risk

The primary objective was not just to create visualizations, but to build a **business-focused credit risk analytics solution** using data cleaning, dimensional modeling, DAX and interactive Power BI reporting.

---

## 🎯 Business Problem

Financial institutions need continuous visibility into their loan portfolios to understand where risk and exposure are concentrated.

This dashboard addresses questions such as:

- Where is the portfolio exposure concentrated?
- Which sectors have higher high-risk exposure?
- Which sectors contribute the most defaulted exposure?
- Which loan types have higher default rates?
- Which credit ratings contribute the most expected loss?
- What percentage of portfolio exposure is classified as high risk?
- How is borrower credit quality distributed?
- What is the overall expected loss and RWA of the portfolio?

---

## 📊 Portfolio Snapshot

| KPI | Value |
|---|---:|
| **Total Loans** | 50K+ |
| **Total EAD** | 164.93 Bn |
| **Default Rate** | 13.90% |
| **Expected Loss** | 1.92 Bn |
| **Risk-Weighted Assets** | 25.49 Bn |
| **High-Risk Exposure** | 8.72% |

> **EAD** = Exposure at Default  
> **PD** = Probability of Default  
> **LGD** = Loss Given Default  
> **RWA** = Risk-Weighted Assets

---

# 🛠️ Tools & Technologies

<p align="center">
  <img src="https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black">
  <img src="https://img.shields.io/badge/Power%20Query-742774?style=for-the-badge&logo=microsoft&logoColor=white">
  <img src="https://img.shields.io/badge/DAX-512BD4?style=for-the-badge&logo=microsoft&logoColor=white">
  <img src="https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white">
  <img src="https://img.shields.io/badge/CSV-1F4E79?style=for-the-badge&logo=files&logoColor=white">
</p>

### Core Skills

- Power BI
- Power Query
- DAX
- Data Modeling
- Data Cleaning
- Data Transformation
- Financial Analytics
- Credit Risk Analytics
- Portfolio Analysis
- Business Intelligence
- Data Visualization
- Data Storytelling

---

# 🗂️ Dataset

The project uses multiple datasets representing loan-level portfolio information and supporting risk analysis.

### Main Datasets

| Dataset | Purpose |
|---|---|
| `loan_portfolio.csv` | Loan-level portfolio and credit-risk information |
| `credit_ratings.csv` | Credit rating information |
| `macro_stress_scenarios.csv` | Macroeconomic stress scenario information |
| `portfolio_metrics.csv` | Portfolio-level metrics |
| `vintage_analysis.csv` | Vintage-level portfolio analysis |

### Loan Portfolio Attributes

The primary loan portfolio contains attributes such as:

- Loan ID
- Origination Date
- Maturity Date
- Maturity Months
- Sector
- Loan Type
- Collateral
- Initial Rating
- Credit Score
- EAD
- Coupon Rate
- Leverage
- Interest Coverage
- Debt-to-Equity
- Annual PD
- LGD
- Expected Loss
- Unexpected Loss
- RWA
- Default Status
- Default Date
- Survival Months
- Recovery Rate
- Loss Given Default

---

# 🧹 Data Preparation & Transformation

Data preparation was performed using **Power Query**.

### Data Cleaning

- Validated column data types
- Checked missing values
- Checked duplicate records
- Standardized date fields
- Validated numeric and categorical fields
- Reviewed risk-related attributes
- Preserved expected null values for non-defaulted loans

For example, fields such as:

```text
default_date
recovery_rate
loss_given_default
