# Customer Shopping Behavior — End-to-End Data Analysis Project

This repository showcases an end-to-end data analytics project lifecycle for **customer shopping behavior data** — from raw CSV ingestion and SQL-based data preparation, through Python-based exploratory analysis, to an interactive Power BI dashboard published on Power BI Service.

## Project Overview

The goal is to analyze customer purchasing patterns — demographics, spending, subscription behavior, discounts, and purchase frequency — to uncover insights that support marketing, retention, and sales strategy decisions.

**Dataset:** `customer_shopping_behavior.csv` — 3,900 customer transaction records, 18 attributes (see dataset README for full column dictionary).

## Project Workflow

1. **Data Ingestion** — Load raw CSV into SQL Server via SSMS
2. **Data Cleaning & Preparation (SQL)** — Handle missing values (e.g. `Review Rating`), validate data types, standardize categorical values
3. **Exploratory Data Analysis (Python)** — Statistical summaries, distribution analysis, correlation checks, segmentation using pandas/matplotlib/seaborn
4. **Data Modeling & Transformation (Power Query)** — Clean and shape data inside Power BI
5. **Dashboard Development (Power BI)** — Build interactive visuals and KPIs
6. **Testing** — Validate calculations, filters, and visuals against source data
7. **Deployment** — Publish report to Power BI Service and configure access/refresh

## Tech Stack

| Stage | Tool |
|---|---|
| Data Storage & Querying | SSMS (SQL Server Management Studio) |
| Data Cleaning & EDA | Python (pandas, numpy, matplotlib/seaborn) |
| Data Modeling & Visualization | Power BI Desktop |
| Calculations | DAX |
| Publishing | Power BI Service |

## SSMS / SQL Tasks

- Import CSV into a SQL Server table (e.g. `Customer_Shopping_Behavior`)
- Data validation queries: null checks, duplicate `Customer ID` checks, range checks on `Age`, `Purchase Amount`
- Aggregation queries: average purchase amount by category/region, customer counts by subscription status
- Views created for Power BI consumption (e.g. `vw_CustomerSummary`, `vw_CategoryPerformance`)

## Python Analysis Tasks

- Data quality checks (missing values, outliers)
- Descriptive statistics on `Age`, `Purchase Amount`, `Review Rating`, `Previous Purchases`
- Category/segment-level breakdowns (e.g. spend by `Category`, `Season`, `Gender`)
- Correlation analysis between `Discount Applied`, `Promo Code Used`, and `Purchase Amount` / `Review Rating`
- Exported cleaned dataset/insights feeding into the Power BI model

## Power BI Dashboard

**Planned Pages:**
- **Overview** — Total customers, total revenue, average purchase amount, KPI cards
- **Customer Demographics** — Age, gender, location breakdown
- **Purchase Behavior** — Category, season, frequency of purchase trends
- **Discounts & Promotions** — Impact of discounts/promo codes on spend and ratings
- **Subscription & Retention** — Subscription status vs. previous purchases and frequency

**Key Measures (DAX):**
- Total Revenue = `SUM(Purchase Amount)`
- Average Purchase Value
- Average Review Rating
- Discount Usage Rate
- Repeat Customer Rate (based on `Previous Purchases`)

## Filters & Slicers

- Category
- Season
- Location (State)
- Gender
- Subscription Status
- Payment Method

## Deployment

1. Publish the `.pbix` report to **Power BI Service**
2. Configure scheduled data refresh (linked to SQL Server source)
3. Set up Row-Level Security (RLS) if role-based access is needed
4. Share dashboard with stakeholders via Power BI Service workspace

## Repository Contents

- `customer_shopping_behavior.csv` — raw dataset
- SQL scripts — data cleaning, validation, and view creation
- Python notebooks/scripts — EDA and preprocessing
- `.pbix` file — Power BI report
- `README.md` — project documentation
