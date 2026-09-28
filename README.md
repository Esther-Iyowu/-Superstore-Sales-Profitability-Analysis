# Superstore-Sales-Profitability-Analysis
> **Where does this store make money, where does it lose it, and why?**

An end-to-end data analysis of four years of retail orders, from cleaning the raw data to finding what drives (and drains) profit, and recommending what the business should change.

---

## Table of Contents
1. [Project Introduction](#project-introduction)
3. [About the Dataset](#about-the-dataset)
4. [Business Problem](#business-problem)
5. [Business Questions](#business-questions)
6. [Data Dictionary](#data-dictionary)
7. [Data Quality Assessment](#data-quality-assessment)
8. [Data Cleaning](#data-cleaning)
9. [Excel Analysis](#excel-analysis)
    [SQL Analysis](#sql-analysis)
11. [Power BI Dashboard](#powerbi-dashboard)
12. [Key Insights](key-insights)
13. [Recommendations](#recommendations)
14. [Conclusions](#conclusions)
15. [Tools used](#tools-used)
16. [Repository Structure](#repository-structure)

---

## Project Introduction

This project uses the **Superstore dataset**, a widely used practice dataset of orders from a US retail store selling **furniture, office supplies, and technology** to consumers, corporate clients, and home offices. The store's sales grew every year after 2015, but growth alone does not show whether the business is healthy. A sale that loses money still counts as a sale.

In this project, I take on the role of a data analyst working for the store's management team. I clean the raw sales data, explore it, and answer specific business questions about profit, discounting, products, regions, and customers. The goal is to turn the data into clear, practical recommendations, not just charts.

**What this project demonstrates**
- Auditing and cleaning a real-world-style dataset, and documenting every change
- Framing a business problem and breaking it into answerable questions
- Exploratory data analysis focused on profitability
- Communicating findings and recommendations to a non-technical audience

---

## About the Dataset

| Item | Detail |
|---|---|
| Dataset | *Sample - Superstore*, a widely used practice dataset of US retail orders (the store itself is not named in the data) |
| Period covered | 3 January 2014 to 30 December 2017 |
| Size (after cleaning) | 9,993 rows and 22 columns |
| Grain | One row = one product line within one order |
| Orders / customers | 5,009 orders from 793 customers |
| Products | 1,894 distinct products (3 categories, 17 sub-categories) |
| Geography | United States: 49 states (48 states plus DC), 4 regions |

### What each column group tells us

| Group | Columns | Used for |
|---|---|---|
| **When** | Order Date, Ship Date, Ship Mode | Trends, seasonality, delivery time |
| **Who** | Customer ID, Customer Name, Segment | Customer value, segment comparison |
| **Where** | Country, City, State, Postal Code, Region | Regional performance |
| **What** | Product ID, Product Key, Category, Sub-Category, Product Name | Product and category performance |
| **How much** | Sales, Quantity, Discount, Profit | Revenue, discounting, profitability |

### Data Dictionary

| # | Column | Type | Description | Example / Values | Notes |
|---|---|---|---|---|---|
| 1 | Row ID | Integer | Row number from the source file | 1 to 9994 | Index only, not for analysis |
| 2 | Order ID | Text | Identifier of the order | CA-2016-152156 | 5,009 unique; repeats across the rows of one order |
| 3 | Order Date | Date | Date the order was placed | 2016-11-08 | Range 2014-01-03 to 2017-12-30 |
| 4 | Ship Date | Date | Date the order was shipped | 2016-11-11 | Never earlier than Order Date; delivery takes 0 to 7 days |
| 5 | Ship Mode | Text (category) | Shipping method | First Class, Same Day, Second Class, Standard Class | 4 values |
| 6 | Customer ID | Text | Identifier of the customer | CG-12520 | 793 unique |
| 7 | Customer Name | Text | Name of the customer | Claire Gute | One name per Customer ID |
| 8 | Segment | Text (category) | Type of customer | Consumer, Corporate, Home Office | 3 values |
| 9 | Country | Text | Country of delivery | United States | Single value, so no analytical use |
| 10 | City | Text | Delivery city | Henderson | 531 unique |
| 11 | State | Text | Delivery state | Kentucky | 49 unique (48 states plus DC); each state sits in one Region |
| 12 | Postal Code | Text | Delivery ZIP code, 5 characters | 42420, 06510 | Stored as text so leading zeros are kept |
| 13 | Region | Text (category) | Sales region | Central, East, South, West | 4 values |
| 14 | Product ID | Text | Product identifier from the source | FUR-BO-10001798 | Prefix shows the category (FUR, OFF, TEC). 32 IDs are reused for two different products, so use Product Key for product-level analysis |
| 15 | Product Key | Text | Unique product identifier | FUR-BO-10001798, FUR-BO-10002213-A | Equals Product ID, except where one ID has two product names; those get a -A or -B suffix. 1,894 unique |
| 16 | Category | Text (category) | Top-level product group | Furniture, Office Supplies, Technology | 3 values |
| 17 | Sub-Category | Text (category) | Product group within a category | Bookcases, Chairs, Phones, ... | 17 values |
| 18 | Product Name | Text | Name of the product | Bush Somerset Collection Bookcase | 16 names appear under more than one Product ID (treated as separate products) |
| 19 | Sales | Decimal | Sales amount for the row | 261.96 | Total for the line, not per unit. Currency not stated; assumed USD |
| 20 | Quantity | Integer | Units sold on the row | 2 | Range 1 to 14 |
| 21 | Discount | Decimal | Discount applied, as a fraction | 0.2 (= 20%) | 12 distinct values from 0 to 0.8 |
| 22 | Profit | Decimal | Profit or loss on the row | 41.91 | Negative means the row lost money |

---

## Business Problem

### Context
Sales rose from about **$484K in 2014 to $733K in 2017** (after a small dip in 2015), reaching roughly **$2.30M in total**. Over the same period, the business earned about **$286K in profit, a margin of 12.5%**. That means only about 12 cents of every dollar sold is kept as profit, and management does not yet know which products, discounts, regions, or customers are pulling that number down.

### Problem statement

> Sales are growing, but the profit margin is low. Which products, discount levels, regions, and customers are losing money, and what should the business change to improve profitability?

### Business questions

1. **Growth vs profit:** Is the business growing profitably, and how do sales and margin change by year and season?
2. **Products:** Which categories and sub-categories make money, and which lose it?
3. **Discounting:** At what discount level do orders stop being profitable, and how much of the total loss comes from heavy discounting?
4. **Regions:** Which regions and states underperform, and what explains the gap?
5. **Loss-making products:** Which individual products cause the biggest losses?
6. **Customers:** Which customers and segments create the profit, and which lose the business money?

### Success criteria
The analysis is successful if it identifies **where** profit is being lost, **why**, and gives management **specific, actionable recommendations** (for example, a discount policy or product review) supported by the data.

---

## Approach
*To be completed: data cleaning, exploratory analysis and tools used.*

## Key Findings
*To be completed after the analysis.*

## Recommendations
*To be completed after the analysis.*

## Repository Structure
```
superstore-analysis/
├── data/
│   ├── Sample - Superstore.xlsx     # raw data
│   └── Superstore_Cleaned.xlsx      # cleaned data, data dictionary, cleaning log
├── analysis/                        # queries, notebooks or workbook with your work
├── visuals/                         # charts and dashboard screenshots
└── README.md
```
