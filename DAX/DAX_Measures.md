# 🧮 DAX Measures & Calculations

This file contains the key DAX measures and calculated columns used in the **Credit Risk & Loan Portfolio Analytics Dashboard**.

---

## 📊 Portfolio KPIs

### Total Loans

```DAX
Total Loans =
COUNTROWS(loan_portfolio)
```

Counts the total number of loans in the portfolio.

---

### Total EAD

```DAX
Total EAD =
SUM(loan_portfolio[ead])
```

Calculates total Exposure at Default (EAD).

---

### Defaulted Loans

```DAX
Defaulted Loans =
CALCULATE(
    COUNTROWS(loan_portfolio),
    loan_portfolio[defaulted] = 1
)
```

Counts the number of loans that have defaulted.

---

### Default Rate

```DAX
Default Rate =
DIVIDE(
    [Defaulted Loans],
    [Total Loans],
    0
)
```

Calculates the percentage of loans that have defaulted.

---

## 💰 Expected Loss & Risk Measures

### Total Expected Loss

```DAX
Total Expected Loss =
SUM(loan_portfolio[el])
```

Calculates the total expected credit loss across the portfolio.

---

### Total RWA

```DAX
Total RWA =
SUM(loan_portfolio[rwa])
```

Calculates total Risk-Weighted Assets.

---

### Average PD

```DAX
Average PD =
AVERAGE(loan_portfolio[pd_annual])
```

Calculates the average annual Probability of Default.

---

### Average LGD

```DAX
Average LGD =
AVERAGE(loan_portfolio[lgd])
```

Calculates the average Loss Given Default.

---

### Average Credit Score

```DAX
Average Credit Score =
AVERAGE(loan_portfolio[credit_score])
```

Calculates the average credit score across the portfolio.

---

### Total Unexpected Loss

```DAX
Total Unexpected Loss =
SUM(loan_portfolio[unexpected_loss])
```

Calculates total unexpected loss across the portfolio.

---

## ⚠️ Risk Classification

### Risk Category

```DAX
Risk Category =
SWITCH(
    TRUE(),
    loan_portfolio[pd_annual] >= 0.10, "High Risk",
    loan_portfolio[pd_annual] >= 0.05, "Medium Risk",
    "Low Risk"
)
```

Classifies loans into Low, Medium and High Risk categories based on annual PD.

---

## 🔴 High Risk Portfolio Analysis

### High Risk Loans

```DAX
High Risk Loans =
CALCULATE(
    [Total Loans],
    loan_portfolio[Risk Category] = "High Risk"
)
```

Counts loans classified as High Risk.

---

### High Risk EAD

```DAX
High Risk EAD =
CALCULATE(
    [Total EAD],
    loan_portfolio[Risk Category] = "High Risk"
)
```

Calculates EAD associated with High Risk loans.

---

### High Risk Exposure %

```DAX
High Risk Exposure % =
DIVIDE(
    [High Risk EAD],
    [Total EAD],
    0
)
```

Calculates the percentage of total portfolio exposure classified as High Risk.

---

## 🔻 Default Exposure Analysis

### Defaulted EAD

```DAX
Defaulted EAD =
CALCULATE(
    [Total EAD],
    loan_portfolio[defaulted] = 1
)
```

Calculates total EAD associated with defaulted loans.

---

### Defaulted EAD %

```DAX
Defaulted EAD % =
DIVIDE(
    [Defaulted EAD],
    [Total EAD],
    0
)
```

Calculates defaulted exposure as a percentage of total portfolio exposure.

---

## 📉 Risk Segment Exposure

### Medium Risk EAD

```DAX
Medium Risk EAD =
CALCULATE(
    [Total EAD],
    loan_portfolio[Risk Category] = "Medium Risk"
)
```

Calculates EAD associated with Medium Risk loans.

---

### Low Risk EAD

```DAX
Low Risk EAD =
CALCULATE(
    [Total EAD],
    loan_portfolio[Risk Category] = "Low Risk"
)
```

Calculates EAD associated with Low Risk loans.

---

## 📈 Risk Ratios

### Expected Loss Rate

```DAX
Expected Loss Rate =
DIVIDE(
    [Total Expected Loss],
    [Total EAD],
    0
)
```

Measures expected loss relative to total portfolio exposure.

---

### RWA to EAD %

```DAX
RWA to EAD % =
DIVIDE(
    [Total RWA],
    [Total EAD],
    0
)
```

Measures Risk-Weighted Assets relative to total Exposure at Default.

---

## 🎯 Credit Score Segmentation

### Credit Score Band

```DAX
Credit Score Band =
SWITCH(
    TRUE(),
    loan_portfolio[credit_score] < 600, "<600",
    loan_portfolio[credit_score] < 650, "600-649",
    loan_portfolio[credit_score] < 700, "650-699",
    loan_portfolio[credit_score] < 750, "700-749",
    loan_portfolio[credit_score] < 800, "750-799",
    "800+"
)
```

Groups borrowers into meaningful credit-score ranges for portfolio analysis.

---

## 📅 Date Table

### Date Table

```DAX
DateTable =
CALENDAR(
    MIN(loan_portfolio[origination_date]),
    MAX(loan_portfolio[maturity_date])
)
```

Creates a continuous date table covering the loan origination and maturity period.

---

### Year

```DAX
Year =
YEAR(DateTable[Date])
```

Extracts the year from the Date column.

---

### Month

```DAX
Month =
FORMAT(DateTable[Date], "MMM")
```

Creates a three-letter month name.

---

### Month Number

```DAX
Month Number =
MONTH(DateTable[Date])
```

Creates a numeric month value for chronological sorting.

---

## 📌 Vintage Analysis

### Vintage

```DAX
Vintage =
YEAR(loan_portfolio[origination_date])
    & "Q"
    & QUARTER(loan_portfolio[origination_date])
```

Creates a quarterly vintage label based on the loan origination date.

Example:

`2025Q1`

---

## 🧠 DAX Concepts Used

The project demonstrates practical use of:

- `CALCULATE()`
- `COUNTROWS()`
- `SUM()`
- `AVERAGE()`
- `DIVIDE()`
- `SWITCH()`
- `TRUE()`
- `YEAR()`
- `MONTH()`
- `FORMAT()`
- `QUARTER()`
- Filter context
- Calculated columns
- Measures
- Date intelligence fundamentals
- Risk segmentation
- Financial KPI calculations

---

## 📊 Key Financial Risk Metrics

| Metric | Description |
|---|---|
| EAD | Exposure at Default |
| PD | Probability of Default |
| LGD | Loss Given Default |
| EL | Expected Loss |
| RWA | Risk-Weighted Assets |
| Default Rate | Defaulted Loans / Total Loans |
| Expected Loss Rate | Expected Loss / Total EAD |
| High Risk Exposure % | High Risk EAD / Total EAD |
| Defaulted EAD % | Defaulted EAD / Total EAD |

---

## 🎯 Purpose of the DAX Layer

The DAX layer converts the raw loan-level data into business-ready financial and credit-risk metrics.

These calculations support:

- Portfolio monitoring
- Credit-risk segmentation
- Default analysis
- Exposure analysis
- Expected-loss analysis
- Risk-weighted asset analysis
- Executive-level decision support
