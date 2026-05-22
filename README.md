# Retail Sales BI Dashboard

## Data Warehouse and Power BI Decision Support Project

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow)
![Power Query](https://img.shields.io/badge/Power%20Query-ETL-green)
![DAX](https://img.shields.io/badge/DAX-Measures-blue)
![Data Warehouse](https://img.shields.io/badge/Data%20Warehouse-Star%20Schema-purple)
![BI](https://img.shields.io/badge/Business%20Intelligence-Retail%20Analytics-orange)

---

## Project Overview

This project presents an end-to-end Business Intelligence solution for analyzing retail sales transactions from shopping malls in Istanbul.

The objective is to transform raw transactional data into a structured decision-support system using:

- data warehouse modeling
- ETL processing in Power Query
- star schema design
- DAX measures
- interactive Power BI dashboards
- sales performance analysis
- short-term revenue forecasting
- automated report delivery through Power BI Service

The final solution helps business users understand revenue performance, customer profiles, product category behavior, payment preferences, and mall-level sales trends.

---

## Business Problem

Retail managers and business analysts need reliable dashboards to answer strategic questions such as:

- Which product categories generate the highest revenue?
- Which shopping malls perform best?
- How does revenue evolve over time?
- What are the most important customer segments?
- Do purchasing behaviors differ by gender or age group?
- Which payment methods dominate sales?
- Can future revenue be estimated using historical trends?

This project addresses these needs by building a complete BI workflow from raw data to interactive reporting.

---

## Dataset

The project uses the Customer Shopping Dataset, containing retail transactions from Istanbul shopping malls.

| Property | Description |
|---|---|
| Dataset | Customer Shopping Dataset |
| Source | Kaggle |
| Format | CSV |
| Volume | 99,457 rows |
| Period | January 2021 to March 2023 |
| Location | 10 shopping malls in Istanbul |
| Domain | Retail sales analytics |

The dataset includes transaction-level information such as:

- invoice number
- customer ID
- gender
- age
- product category
- quantity
- price
- payment method
- invoice date
- shopping mall

---

## Functional Objectives

The BI system was designed for different decision-making profiles:

| User Profile | Role | Information Need |
|---|---|---|
| Commercial Director | Decision-maker | Global revenue tracking and mall performance comparison |
| Marketing Manager | Decision-maker | Customer segmentation by gender and age |
| Data Analyst | Analyst | Detailed exploration and cross-analysis |
| Mall Manager | Decision-maker | Performance of a specific mall and dominant categories |

---

## Data Warehouse Design

A dimensional model was designed using a star schema.

This modeling choice was selected because it is:

- simple to query
- compatible with Power BI
- efficient for medium-sized analytical datasets
- easy for non-technical users to understand

The grain of the fact table is one sales transaction.

---

## Star Schema

The data warehouse contains:

- 1 fact table
- 5 dimension tables

### Fact Table

| Table | Description |
|---|---|
| `Fact_Sales` | Stores transaction-level sales facts |

Main columns:

- invoice number
- customer ID
- category ID
- payment ID
- date ID
- mall ID
- quantity
- price
- total revenue
- total transactions

### Dimension Tables

| Dimension | Description |
|---|---|
| `Dim_Client` | Customer demographic information |
| `Dim_Date` | Date attributes: day, month, quarter, year |
| `Dim_Category` | Product category information |
| `Dim_Payment` | Payment method information |
| `Dim_Location` | Shopping mall information |

---

## ETL Pipeline

The ETL process was implemented in Power Query.

### Extraction

The CSV file was imported into Power BI Desktop through:

```text
Home > Get Data > Text/CSV