# 🛡️ Insurance Analytics Dashboard — Project 

A comprehensive end-to-end insurance analytics project that ingests raw brokerage, invoice, meeting, and opportunity data to deliver actionable KPI dashboards across **Excel**, **Tableau**, **Power BI**, and **MySQL**.

---

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Dataset Description](#dataset-description)
- [KPI Analysis](#kpi-analysis)
- [Project Structure](#project-structure)
- [Tools & Technologies](#tools--technologies)
- [Dashboard Highlights](#dashboard-highlights)
- [Key Findings & Conclusion](#key-findings--conclusion)
- [Recommendations](#recommendations)
- [How to Use](#how-to-use)

---

## 🎯 Project Overview

This project was built to support **branch-level performance discussions** between corporate teams and individual branch heads. It provides:

- A summary of new, cross-sell, and renewal business numbers per branch
- Performance metrics for each Account Executive
- Budget vs. achievement tracking across income classes
- Pipeline visibility through opportunity stage analysis


---

## 📂 Dataset Description

All source data is stored as CSV files and loaded into a MySQL database (`Insurance_Analysis`).

| File | Table | Rows | Description |
|------|-------|------|-------------|
| `Brokerage_fees.csv` | `brokerage_fees` | ~970 | Client policy details — income class, amount, renewal status, product group |
| `brokerage_csv.csv` | *(raw brokerage)* | ~961 | Extended brokerage data with Account Exe ID, lapse reason, and last updated date |
| `Invoice.csv` | `invoice` | ~204 | Invoices raised per Account Executive — invoice number, date, amount, income class |
| `Meeting_List.csv` | `meeting list` | ~34 | Meetings tracked by Account Executive — branch, attendees, and year |
| `Opportunity.csv` | `opportunity` | ~49 | Sales pipeline — opportunity name, stage, revenue amount, product group, risk details |
| `Individual_Budget.csv` | `individual_budget` | ~18 | Budget targets per employee — New, Cross-Sell, and Renewal budget allocations |
| `Fees.csv` | *(fees)* | ~9 | Client fee transactions by salesperson and branch |
| `Bridge_Table.csv` | `bridge_table` | ~13 | Mapping of Sr. No → Account Executive names |
| `Income_class_bridge.csv` | *(lookup)* | 3 | Lookup table for income classes: Cross Sell, Renewal, New |

---

## 📊 KPI Analysis

Six core KPIs are tracked across the dashboards:

| # | KPI | Description |
|---|-----|-------------|
| 1 | **Invoice Count by Account Executive** | Number of invoices raised per AE, segmented by income class |
| 2 | **Yearly Meeting Count** | Total meetings conducted per year |
| 3 | **Target vs. Achieved vs. Invoice** | Budget attainment % for Cross-Sell, New, and Renewal income classes (Placed % & Invoice %) |
| 4 | **Stage Funnel by Revenue** | Revenue aggregated by opportunity stage (pipeline funnel) |
| 5 | **Meetings by Account Executive** | Individual meeting count per AE |
| 6 | **Top 5 Opportunities by Revenue** | Highest-value open opportunities in the pipeline |

### KPI 3 — Income Class Performance Summary

| Income Class | Target | Achieved | Invoiced | Placed % | Invoice % |
|---|---|---|---|---|---|
| Cross Sell | ₹20.08 M | ₹13.04 M | ₹2.85 M | 178.39% ▲ | 39.15% ▼ |
| New | ₹19.67 M | ₹3.53 M | ₹0.57 M | 82.47% ▼ | 13.9% ▼ |
| Renewal | ₹12.32 M | ₹18.51 M | ₹8.24 M | 210.76% ▲ | 98.99% ▼ |

---

## 🗂️ Project Structure

```
Insurance-Analytics/
│
├── data/                          # Raw source data
│   ├── Bridge_Table.csv
│   ├── brokerage_csv.csv
│   ├── Brokerage_fees.csv
│   ├── Fees.csv
│   ├── Income_class_bridge.csv
│   ├── Individual_Budget.csv
│   ├── Invoice.csv
│   ├── Meeting_List.csv
│   └── Opportunity.csv
│
├── sql/
│   └── Insurance_Analytics_SQL.sql   # DB creation, KPI queries & stored procedure
│
├── dashboards/
│   ├── Insurance_Analytics_Excel.xlsx     # Excel dashboard with pivot summaries
│   ├── Insurance_Analytics_Tableau.twbx   # Tableau packaged workbook
│   ├── Insurance_Analytics_PowerBI.pbix   # Power BI report
│   └── Insurance_Analytics.pptx          # Final presentation deck
│
└── README.md
```

---

## 🛠️ Tools & Technologies

- **Database:** MySQL — database creation, KPI queries, stored procedures
- **Excel:** Pivot tables, KPI summary dashboard, budget vs. actuals
- **Tableau:** Interactive visual dashboard (`.twbx`)
- **Power BI:** Business intelligence report (`.pbix`)
- **Python / pandas** *(data prep)*

---

## 📈 Dashboard Highlights

- **49 total opportunities** tracked; **44 open** in the pipeline
- **Renewal** segment is the strongest performer — 210.76% placement achievement
- **Cross-Sell** delivers the highest profit margin at **64.94%**
- **New** business is the weakest segment with only 82.47% placement and 13.9% invoicing

---

## 🔍 Key Findings & Conclusion

### New Policies
- Total Budget: **₹19.674 M** | Revenue Achieved: **₹3.532 M** | Profit Margin: **17.95%**
- Growth Rate: 2.90% — steady but needs acceleration

### Cross-Sell Policies
- Total Budget: **₹20.083 M** | Revenue Achieved: **₹13.041 M** | Profit Margin: **64.94%**
- Growth Rate: 14.21% — high profitability; cross-selling opportunities should be leveraged further

### Renewal Policies
- Total Budget: **₹12.32 M** | Revenue Achieved: **₹18.507 M** | Profit Margin: **150.23%**
- Growth Rate: 66.92% — exceptional performance; strong focus should be maintained

---

## 💡 Recommendations

1. **Enhance Customer Service** — Implement AI-driven chatbots for 24/7 support; train staff on engagement and conflict resolution
2. **Expand Product Offerings** — Introduce products tailored to emerging markets; bundle for better value
3. **Increase Sales & Retention** — Launch personalized marketing campaigns; introduce loyalty programs
4. **Market Analysis** — Conduct regular research on customer needs; adapt strategies based on competitive analysis
5. **Employee Engagement** — Foster positive work culture; introduce recognition programs to retain top talent
6. **Operational Efficiency** — Regular technology training; encourage cross-team collaboration

---


