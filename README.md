# Customer Churn Analysis – Power BI Dashboard

An end-to-end customer churn analysis of a telecom dataset. The project cleans messy raw data, measures churn with DAX, and presents the findings in an interactive Power BI dashboard that highlights why customers leave and which customers are at high risk.



## Objective
- Measure the overall churn rate
- Find which customer groups (contract, tenure, services) churn the most
- Flag high-risk customers
- Suggest ways to improve retention

## Dataset
- File: `telco_churn_unclean.csv`
- Size: 7,048 rows and 21 columns (7,043 unique customers after removing duplicates)
- Target column: `Churn` (Yes/No)
- Contents: customer demographics (gender, senior citizen, partner, dependents), account information (tenure, contract, payment method, paperless billing), services (phone, internet, online security, backup, streaming, etc.) and charges (monthly and total)

## Tools Used
- Microsoft Excel
- Power BI Desktop
- Power Query
- DAX

## Data Cleaning (Power Query)
The raw file was intentionally messy. Issues found and fixed:
- 5 duplicate rows removed
- `MonthlyCharges` stored as text, with some values containing a `$` sign – symbol removed and converted to a number
- 134 blank or non-numeric values in `TotalCharges` – handled and converted to a number
- Inconsistent labels in `Contract` (`month to month` vs `Month-to-month`) – standardized
- Extra trailing spaces in `PaymentMethod` – trimmed

## DAX Measures and Columns
- Total Customers, Churned Customers, Churn Rate %
- Average monthly charges for retained vs churned customers
- Tenure Band (0–6 months, 6–12 months, 12+ months)
- Customer Type (Existing / New)
- Risk Type (Normal / High Risk) for retained customers

## Key Insights
- **7,043** total customers, **1,869** churned, giving an overall churn rate of **26.54%**
- **Month-to-month contracts drive churn:** 1,655 of the 1,869 churned customers (about 89%) were on month-to-month contracts, compared with 166 on one-year and 48 on two-year contracts
- **New customers are the most at risk:** churn rate is 52.94% in the first 6 months, 35.89% at 6–12 months, and 17.13% after 12 months
- **Churned customers pay more:** average monthly charges are about $74 for churned customers vs about $61 for retained customers
- **633 retained customers are flagged High Risk** and are good targets for retention campaigns

## Recommendations
- Offer discounts or benefits to move month-to-month customers onto one- or two-year contracts
- Build onboarding and engagement programs for the first 6 months, when churn is highest
- Review pricing and plan fit for high-spending customers who are leaving
- Contact the high-risk group early with retention offers

## Repository Structure
```
customer-churn-analysis/
├── data/
│   └── telco_churn_unclean.csv
├── images/
│   └── dashboard.png
├── Customer_Churn_Dashboard.pbix
├── Churn_DataSet_Dashboard.pdf
├── churn_analysis.py
└── README.md
```

## How to Use
1. Download or clone the repository
2. Open `Customer_Churn_Dashboard.pbix` in Power BI Desktop
3. If Power BI cannot find the data, go to Transform data → Data source settings and point it to `data/telco_churn_unclean.csv`


```

## Author
**Om Jawale**
GitHub: https://github.com/omjawale-oma
