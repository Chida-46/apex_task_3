# Customer Segmentation & Sales Performance Analysis

**ApexPlanet Internship — Task 3: Deep-Dive Analysis & Interactive Dashboarding**

This project analyzes sales performance and customer purchasing patterns using a cleaned Excel dataset and a Power BI dashboard. The analysis focuses on five core KPIs and a customer age-group segmentation deep-dive, with additional views by product, category, city, gender, and month.

## Project Objectives

- Define and calculate five business KPIs.
- Understand overall sales performance.
- Compare revenue contribution across customer age groups.
- Identify leading products, product categories, and cities by recorded revenue.
- Build an interactive Power BI report for business users.
- Present findings and practical recommendations.

## Repository Structure

```text
Customer-Segmentation-Sales-Analysis/
│
├── Dataset/
│   └── apexplanet_cleaned_sales.xlsx
│
├── Dashboard/
│   └── apex.pbix
│
├── Report/
│   ├── ApexPlanet_Task3_Deep_Dive_Report.pdf
│   └── ApexPlanet_Task3_Deep_Dive_Report.docx
│
├── Screenshots/
│   ├── Dashboard_Overview.png
│   └── Customer_Segmentation.png
│
└── README.md
```

> Update the filenames above if your uploaded files use different names. Only include the dataset if you are permitted to redistribute it.

## Dataset Overview

The analysis uses `apexplanet_cleaned_sales.xlsx`. The workbook contains order and customer identifiers, order dates, customer demographics, city, product, category, quantity, unit price, total sales, and derived fields such as customer age group and sales month.

- Records: **[insert verified row count]**
- Date coverage: **[insert start date – end date]**
- Currency: **[confirm currency from the data source]**

The workbook does not explicitly establish a currency code in the analysis documentation. Confirm the correct currency before presenting currency symbols in the dashboard or report.

## Data Preparation and Validation

The workbook was imported into Power BI using **Get Data → Excel Workbook → Transform Data**. Validation included:

- Checking column names and data types.
- Reviewing missing values and exact duplicate rows.
- Confirming sales calculations using the supplied validation fields.
- Checking unique order and customer identifiers.
- Reviewing unknown city values and consistency of customer age-group assignments.
- Creating a date table and a numeric year-month sort key to display months chronologically.

**Data-quality considerations:** Some customer IDs appear in more than one age group, so distinct customer counts by segment may overlap. The final month in the dataset may be incomplete; compare only complete periods when evaluating monthly trends. Review these issues before making business decisions.

## Core KPIs

The five KPIs are defined as follows. The DAX assumes the imported fact table is named `Sales` and that the relevant fields have these exact names.

| KPI | DAX / Formula | Business purpose |
|---|---|---|
| Total Revenue | `SUM(Sales[Total_Sales])` | Measures the total recorded sales value. |
| Total Orders | `DISTINCTCOUNT(Sales[Order_ID])` | Counts unique orders rather than transaction rows. |
| Average Order Value (AOV) | `DIVIDE([Total Revenue], [Total Orders], 0)` | Measures average revenue per unique order. |
| Total Customers | `DISTINCTCOUNT(Sales[Customer_ID])` | Counts unique customers in the selected filter context. |
| Revenue per Customer | `DIVIDE([Total Revenue], [Total Customers], 0)` | Measures revenue per distinct customer. |

### DAX Measures

```DAX
Total Revenue =
SUM(Sales[Total_Sales])

Total Orders =
DISTINCTCOUNT(Sales[Order_ID])

Average Order Value =
DIVIDE([Total Revenue], [Total Orders], 0)

Total Customers =
DISTINCTCOUNT(Sales[Customer_ID])

Revenue per Customer =
DIVIDE([Total Revenue], [Total Customers], 0)
```

## Deep-Dive Analysis: Customer Segmentation

Customer age groups are compared using the `Customer_Age_Group` field. The analysis examines:

- Revenue by customer age group.
- Distinct customers by age group.
- Revenue per customer by age group.

The uploaded workbook analysis found that the **36–45 age group** had the highest recorded revenue among the age groups. This is a revenue comparison only; it does not establish profitability, customer retention, or customer lifetime value.

Because some customer IDs occur in more than one age group, validate customer-level age-group consistency before treating segment customer counts or revenue-per-customer comparisons as definitive.

## Additional Sales Analysis

The dashboard also explores:

- **Category:** revenue by `Category`.
- **Product:** revenue by individual `Product`.
- **Geography:** revenue by `City`.
- **Time:** monthly revenue trend using the date table.
- **Demographics:** sales by gender and customer age group.

The workbook analysis identified **Electronics** as the highest-revenue category. Refer to the detailed report and dashboard for the exact calculated values and rankings.

## Power BI Dashboard

The report is designed around two analytical themes:

1. **Sales overview:** KPI cards, monthly revenue trend, product and category revenue, and city performance.
2. **Customer segmentation:** customer counts, revenue, and revenue per customer by age group.

Planned slicers allow users to filter by:

- City
- Category
- Gender
- Customer age group
- Order date

Before publishing, test each slicer in Power BI Desktop and confirm that all intended visuals and KPI cards respond correctly. Also verify the KPI calculations against the source workbook.

## Key Business Recommendations

- Investigate the purchasing behavior of the highest-revenue age group and test relevant targeted campaigns.
- Review Electronics product mix, stock availability, and margin before making inventory decisions.
- Compare product revenue with profit margin, returns, and stock costs before prioritizing products.
- Review records with unknown city values before using geographic results for market allocation.
- Compare complete months with complete months; clearly label partial periods.
- Resolve inconsistent age-group assignments before relying on customer-segment counts.

## Project Deliverables

- Power BI dashboard: `Dashboard/apex.pbix`
- Deep-dive report: `Report/ApexPlanet_Task3_Deep_Dive_Report.pdf`
- Editable report: `Report/ApexPlanet_Task3_Deep_Dive_Report.docx`
- Dashboard screenshots: `Screenshots/`
- This project README.

### Live Dashboard

**Power BI report link:** [Add your published Power BI report URL here]

### Demo Video

**LinkedIn demonstration:** [Add your LinkedIn video URL here]

## How to View the Project

1. Download the `.pbix` file from the `Dashboard` folder.
2. Open it using Microsoft Power BI Desktop.
3. Review the KPI cards and charts.
4. Use the slicers to explore sales by city, category, gender, age group, and date.
5. Refer to the PDF report for the methodology, findings, and recommendations.

## Conclusion

This project brings together sales KPIs, customer age-group segmentation, and product, category, geographic, and time-based analysis in an interactive Power BI report. It provides a starting point for data-informed decisions while documenting data-quality limitations that should be addressed before operational use.

---

**Prepared for:** ApexPlanet Internship — Task 3  
**Project:** Customer Segmentation & Sales Performance Analysis

