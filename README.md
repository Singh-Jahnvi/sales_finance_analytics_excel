# Sales & Finance Analytics Dashboard
### Solstice Distributors, FY 2023-24 (Consumer Electronics & Home Appliances B2B Distribution)

## About This Project

This is an end-to-end sales and finance analytics project built in Excel for a fictional B2B distribution company called Solstice Distributors, covering FY 2023-24. The company sells consumer electronics and home appliances across four regions in India.

I built this to practice the full analytics workflow. The raw sales data was made deliberately messy on purpose, so I could practice real data cleaning the way it actually shows up on the job, instead of working with a dataset that is already clean.

## Problem Statement

The project was built to answer a few business questions:

- How is revenue and profit trending month over month, and where are margins weakest?
- Which regions and product categories bring in the most revenue?
- Which customers matter most, and where is payment risk (like overdue orders) concentrated?
- Can the sales data and the finance data be combined into one P&L view, instead of two separate spreadsheets that someone has to update by hand every month?

## The Data

Two raw files were used:

- `Sales_Raw_Data_FY2023-24.xlsx` (4,284 rows, deliberately messy)
- `Operating_Expenses_FY2023-24.xlsx` (72 rows, monthly expense categories)

Before cleaning, the sales file had these issues:

- A small number of exact duplicate rows
- Order_Date in five different formats: real dates, DD-MM-YYYY, MM/DD/YYYY, YYYY.MM.DD, and DD Mon YYYY as text
- Region and Product_Category with inconsistent casing and stray spaces
- Customer_Name with extra whitespace and random uppercase
- Unit_Price stored as text with a ₹ symbol and commas for some rows
- Missing Discount_Pct (about 6% of rows) and missing Payment_Status (about 4% of rows)
- Negative Quantity values for a handful of rows
- A few fully blank rows

## What I Did

**Data cleaning (Power Query)**

Cleaned the raw dataset using Power Query: removed duplicates and blank rows, trimmed and standardized text casing for Region, Product_Category, and Customer_Name, converted Unit_Price from text to a proper number, fixed the negative Quantity values, filled missing Discount_Pct and Payment_Status values, and standardized mixed Order_Date formats before converting them into a consistent date type.

**Data modeling (Power Pivot)**

Loaded the cleaned Sales and Operating Expenses tables into the Excel Data Model, added a Calendar table covering the full financial year, and built relationships between the tables to support monthly financial reporting using DAX measures and PivotTables.

**DAX measures**

Wrote measures for Total Revenue, Total COGS, Gross Profit, Gross Margin %, Total Operating Expenses, Net Profit, Net Margin %, Total Orders, and Average Order Value.

**PivotTables and dashboard**

Built a P&L summary by month, a revenue breakdown by region and category, a monthly trend view with a line chart, a top 10 customers view, and a payment status breakdown. All of these come together on one dashboard page with slicers for region, category, and payment status.

## Key Insights

- Total revenue for FY 2023-24 came to about ₹21.72 crore, with an overall gross margin of 31.09%.
- North region generated the highest revenue among all four sales regions.
- Deepak Distributors was the top customer by revenue among the top 10 accounts.

## Tools Used

Excel, Power Query, Power Pivot, DAX, PivotTables, PivotCharts

## Files in This Repo

- `Sales_Raw_Data_FY2023-24.xlsx` - raw, messy transactional data
- `Operating_Expenses_FY2023-24.xlsx` - raw monthly expense data
- `Sales_Finance_Analytics_Project.xlsx` - final workbook with cleaned data, data model, and dashboard
- `Dashboard.png` - final interactive sales and finance dashboard
- `P&L_Summary.png` - monthly profit and loss summary report

## Future Improvements

- Customer profitability analysis
- Product profitability analysis
- Budget vs actual reporting
- Simple sales forecasting
- Returns and refund analysis

