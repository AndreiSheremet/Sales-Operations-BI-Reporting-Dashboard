# Sales-Operations-BI-Reporting-Dashboard

## Project Overview

This project is an end-to-end Power BI reporting dashboard built on a public B2B CRM sales opportunities dataset.  
The goal of the project is to analyze sales pipeline performance, sales team performance, and data quality after cleaning.

The dashboard was designed as a small business intelligence reporting solution for a sales / operations team. It includes KPI definitions, data cleaning, relationship modelling, interactive filters, and post-cleaning data quality checks.

## Dataset

The project uses a public CRM sales opportunities dataset with several related tables:

- `sales_pipeline.csv` — sales opportunities and deal stages
- `accounts.csv` — customer account information
- `products.csv` — product information
- `sales_teams.csv` — sales agents, managers, and regional offices
- `data_dictionary.csv` — field descriptions

The dataset represents a fictional B2B sales pipeline for computer hardware products.

## Tools Used

- Power BI Desktop
- Power Query
- DAX
- CSV data modelling
- Data quality checks

## Data Model

The dashboard uses a simple star-schema style model:

- `sales_pipeline` as the main fact table
- `accounts`, `products`, and `sales_teams` as dimension tables

Relationships:

- `sales_pipeline[account]` → `accounts[account]`
- `sales_pipeline[product]` → `products[product]`
- `sales_pipeline[sales_agent]` → `sales_teams[sales_agent]`

## Data Cleaning

The following cleaning steps were performed in Power Query:

- Standardized date and numeric data types
- Fixed product naming mismatch: `GTXPro` → `GTX Pro`
- Fixed sector typo: `technolgy` → `technology`
- Removed incorrect header row from the sales team table
- Created relationships between sales, accounts, products, and sales teams
- Validated opportunity IDs and date logic

## Key KPIs

The dashboard includes the following KPI measures:

- Won Revenue
- Total Opportunities
- Closed Opportunities
- Win Rate
- Average Deal Size
- Average Sales Cycle
- Missing Accounts
- Missing Close Dates
- Missing Engage Dates
- Duplicate IDs
- Invalid Date Records

## Dashboard Pages

### 1. Sales & Operations Overview

This page provides a high-level overview of sales performance in 2017.

It includes:

- Won Revenue
- Total Opportunities
- Closed Opportunities
- Win Rate
- Average Deal Size
- Average Sales Cycle
- Won Revenue by close month
- Won Revenue by product
- Won Revenue by regional office
- Opportunities by deal stage
- Interactive filters for sector, product, and regional office

![Sales & Operations Overview](screenshots/Sales overview)

### 2. Sales Teams Performance

This page focuses on sales agent and manager performance.

It includes:

- Average Sales Cycle by Manager
- Won Revenue by Manager
- Top Sales Agents by Win Rate
- Sales Agents by Won Revenue
- Interactive filters for regional office, product, and manager

![Sales Teams Performance](screenshots/Sales teams)

### 3. Post-Cleaning Data Quality Summary

This page documents the post-cleaning validation checks and remaining reporting limitations.

It includes:

- Records checked
- Missing accounts
- Duplicate IDs
- Missing engage dates
- Missing close dates
- Invalid date records
- Data quality check table with business impact
- Cleaning actions performed
- Reporting limitations

![Post-Cleaning Data Quality Summary](screenshots/Post-cleaning summary)

## Data Quality Findings

The main data quality findings were:

- No duplicate opportunity IDs were found.
- No invalid date records were found, meaning sales cycle calculations are reliable.
- Missing close dates are expected for open opportunities.
- Missing accounts limit account-level and sector-level analysis.
- Missing engage dates are expected for opportunities still in the prospecting stage.

## Business Insights

Some key insights from the dashboard:

- `GTX Pro` generated the highest won revenue among products.
- The West regional office generated the highest won revenue.
- The overall win rate was approximately 63%.
- Average sales cycle was around 48 days.
- Sales performance varies significantly across individual agents and managers.

## Reporting Limitations

- The dataset is fictional and intended for BI practice.
- Open opportunities do not have close dates or final revenue values.
- Account and sector analysis excludes opportunities with missing account values.
- Data quality checks were documented to make KPI reporting more transparent.

## Project Files

- `Power BI project.pbix` — Power BI dashboard file
- `data/` — source CSV files
- `screenshots/` — dashboard page screenshots
- `README.md` — project documentation

## Purpose

This project demonstrates practical skills in:

- Power BI dashboard development
- DAX KPI creation
- Data cleaning in Power Query
- Data modelling and relationships
- Sales and operations reporting
- Data quality validation
- Communicating business insights from data
