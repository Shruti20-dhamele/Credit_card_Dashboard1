# Credit_card_Dashboard1
Credit Card Financial Dashboard | Power BI

# Project Overview

A comprehensive Credit Card Weekly Dashboard built using Power BI, SQL, and DAX to provide real-time insights into key financial performance metrics. The dashboard enables stakeholders to monitor credit card operations, track customer behavior, and make data-driven business decisions.

 Reduced manual reporting time by *35%* using dynamic visuals and auto-refresh slicers.

# Tech Stack

| Tool | Usage |
|------|-------|
| *Power BI Desktop* | Dashboard design, data modeling, visualizations |
| *DAX* | Custom KPI measures — Monthly Spend, Delinquency Rate, Segmentation |
| *SQL* | Data extraction, table joins, data cleaning |
| *Power Query* | Data transformation and loading |
| *CSV / Excel* | Raw data source (10,000+ records) |

#  Dataset

| File | Description |
|------|-------------|
| `credit_card.csv` | 10,109 credit card transaction records |
| `customer.csv` | Customer demographic and profile data |
| `cc_add.csv` | Additional credit card data |
| `cust_add.csv` | Additional customer address data |

#  Key Features

- Real-time KPI Tracking — Monthly Revenue, Total Spend, Transaction Count, Delinquency Rate
- Customer Segmentation — by income group, card category, and job type
-  Dynamic Slicers & Filters— week, quarter, card type, customer segment
-  Star Schema Data Model — fact table (transactions) + dimension tables (customer, address)
-  Week-over-Week Analysis — trend comparison using DAX time intelligence
-  Two Dashboard Views — Transaction Report & Customer Report


#  Key DAX Measures

dax
- Weekly Revenue
Current_week_Revenue = CALCULATE(
    SUM(credit_card[Revenue]),
    FILTER(ALL(credit_card), credit_card[week_num2] = MAX(credit_card[week_num2]))
)

- Delinquency Rate
Delinquency_Rate = DIVIDE(
    CALCULATE(COUNT(credit_card[Client_Num]), credit_card[Delinquent_Acc] = 1),
    COUNT(credit_card[Client_Num])
)

- Revenue WoW Change %
Revenue_WoW_Change = DIVIDE(
    ([Current_week_Revenue] - [Previous_week_Revenue]),
    [Previous_week_Revenue]
)

#  Key Insights from Dashboard

- Total Revenue: ₹55M+ across all weeks
- Top Card Category: Blue card contributes ~83% of total transactions
- Top Customer Segment: Businessmen and White-collar employees drive highest spend
- Delinquency Rate: Monitored weekly to flag at-risk accounts early
- Top States by Revenue: TX, NY, CA contribute highest transaction volume

---

# Dashboard Preview

Transaction Report

[Transaction Report](Transcation%20report.pdf)

Customer Report

[Customer Report](credit%20crad%20customer%20report.pdf)

 How to Run

1. Clone this repository
2. Open **Power BI Desktop**
3. Load `credit_card.csv` and `customer.csv` as data sources
4. Refresh the data model
5. Explore the interactive dashboard with slicers


 Author

Shruti Rajesh Dhamele
M.Sc Computer Science | Data Analyst | Power BI Developer

🔗 [LinkedIn](https://linkedin.com/in/shruti-dhamele-63b025222) | [GitHub](https://github.com/Shruti20-dhamele)
