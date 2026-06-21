# 💳 Credit Risk & Loan Default Analysis — Power BI Dashboard

A 4-page executive dashboard analyzing default risk across a **$303M loan portfolio**, identifying which borrower and loan characteristics drive defaults — and quantifying the trade-offs of acting on them.

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-217346?style=flat-square)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)

**Dataset:** [Credit Risk Dataset (Kaggle)](https://www.kaggle.com/datasets/laotse/credit-risk-dataset) — public dataset of loan applicants with grade, intent, income, home ownership, credit history, and default outcomes.

---

## 📊 Page 1 — Executive Overview

![Executive Overview](screenshots/Executive%20Overview.png)

- **$303M** total loan amount, of which **$76M** is at risk and **$227M** is safe
- Overall **default rate of 22.01%**
- Default rate climbs sharply by loan grade — Grade G loans default at nearly 100%, vs. single digits for Grade A
- 63% of the portfolio sits in the "Low Risk" category by value, but the 5% in "High Risk" still represents $16M of exposure
- **Debt consolidation** is the riskiest loan intent by default rate, ahead of medical and home improvement loans

## 🧑 Page 2 — Borrower Risk Profile: Who is Defaulting?

![Borrower Risk Profile](screenshots/Borrower%20Risk%20Profile.png)

- Defaulters pay a meaningfully higher average interest rate (13.03%) than those who repay (10.44%) — pricing already reflects some of the risk, but not enough to offset it
- Default rate falls steadily as income bracket rises, from ~40% for low income to a small fraction for high income
- Borrowers with a **prior default on file** default again at a visibly higher rate than those without
- Renters and "other" home-ownership statuses default far more than homeowners
- **Unemployed/student** borrowers default at the highest rate of any employment bracket; experienced borrowers default least

## 📐 Page 3 — Loan Characteristics: What Makes a Loan Risky?

![Loan Characteristics](screenshots/Loan%20Characteristics.png)

- **Loan-to-income ratio is one of the strongest predictors**: loans classified "Dangerous" (>60% of income) default at ~78%, vs. under 10% for "Very Affordable" (≤10%) loans
- A grade × intent heatmap pinpoints the worst combinations — e.g., Grade D–G debt consolidation loans default at 90–100%
- Very large loans (>$30K) default noticeably more often than small loans
- **Interest rate threshold is a clean dividing line**: loans priced "Very High" (>20%) default at ~95%, compared to ~5–10% for "Low" (5–10%) priced loans

## 🎯 Page 4 — Executive Summary: Key Insights & Actions

![Executive Summary](screenshots/Executive%20Summary.png)

Turned the analysis into concrete lending-policy recommendations:

**Top 3 risk segments to stop lending to or reprice:**
| Segment | Default Rate | Amount at Risk | Loan Count |
|---|---|---|---|
| Grade F + Debt Consolidation | 100% | $797K | 52 |
| Grade F/G + Medical | 96.83% | $903K | 61 |
| Grade D/E + Debt Consolidation | 94.09% | $8M | 685 |

**Policy scenario — eliminate Grade F & G loans:**
- Default rate cut: **4.56 percentage points**
- Revenue lost: only **1.46%**
- An asymmetric, favorable trade-off for the lender

**Ideal borrower profile** (Grade A/B + Owns home + Venture loan): **0.03% default rate** across 546 loans — a near risk-free segment worth growing.

---

## 🛠️ Tech Stack

- **Power BI** — data modeling, DAX measures, multi-page dashboard design
- **Power Query** — data cleaning and transformation
- **Python (Pandas)** — exploratory data analysis prior to building the model

## 📁 Project Structure

```
credit-risk-loan-dashboard/
├── credit_risk_dashboard.pbix     # Power BI dashboard file
├── notebooks/
│   └── Credit_risk.ipynb           # Exploratory data analysis
├── data/
│   └── credit_risk_dataset.csv    # Source dataset (Kaggle)
├── screenshots/
│   ├── Executive Overview.png
│   ├── Borrower Risk Profile.png
│   ├── Loan Characteristics.png
│   └── Executive Summary.png
└── README.md
```

## 🚀 Viewing the Dashboard

Power BI Desktop is required to open `credit_risk_dashboard.pbix` interactively. If you don't have it installed, the screenshots above capture all four pages in full.
