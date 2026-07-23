# 📊 Marketing Campaign Analytics

## 📌 Project Overview

This project is an end-to-end Marketing Campaign Analytics project developed using Python, Pandas, NumPy, Power BI, and DAX.

The objective is to analyze marketing campaign performance across different:

- Marketing Channels
- Regions
- Products
- Campaigns
- Time Periods

The project demonstrates the complete data analytics workflow from raw data preparation to interactive business intelligence dashboards.

---

## 🔄 End-to-End Workflow

```text
Raw Excel Data
      ↓
Python / Pandas
      ↓
Data Cleaning
      ↓
Data Quality Validation
      ↓
Processed CSV Files
      ↓
Power BI Data Model
      ↓
Star Schema
      ↓
DAX Measures
      ↓
Interactive Dashboard
      ↓
Business Insights
🎯 Business Problem

Marketing teams invest budgets across multiple campaigns and channels. However, raw marketing data does not always provide clear answers to important business questions:

Which marketing channel generates the highest revenue?
Which channel has the best CTR?
Which campaigns generate the most conversions?
Which regions perform best?
Which products generate the highest revenue?
How efficiently is the marketing budget being used?
What is the return on marketing investment?

This project addresses these questions through data preparation, data modeling, DAX calculations, and interactive Power BI dashboards.

🐍 Python Data Preparation

Python and Pandas were used for:

Loading raw marketing data
Exploring the dataset
Checking data types
Handling missing values
Removing duplicate records
Cleaning text fields
Validating business rules
Preparing data for Power BI
Main Python Workflow
import pandas as pd
import numpy as np

# Load data
df = pd.read_excel("marketing_campaign.xlsx")

# Inspect data
print(df.head())
print(df.shape)
print(df.info())

# Check missing values
print(df.isnull().sum())

# Remove duplicates
df = df.drop_duplicates()

# Convert date column
df["Date"] = pd.to_datetime(df["Date"])
✅ Data Quality Validation

Business rules were applied to validate the marketing data.

Clicks cannot exceed impressions
invalid_clicks = df[
    df["Clicks"] > df["Impressions"]
]

print("Invalid click records:", len(invalid_clicks))

Business Rule:

Clicks ≤ Impressions
Conversions cannot exceed clicks
invalid_conversions = df[
    df["Conversions"] > df["Clicks"]
]

print(
    "Invalid conversion records:",
    len(invalid_conversions)
)

Business Rule:

Conversions ≤ Clicks
Spend cannot be negative
invalid_spend = df[
    df["Spend"] < 0
]

Business Rule:

Spend ≥ 0
Revenue cannot be negative
invalid_revenue = df[
    df["Revenue"] < 0
]

Business Rule:

Revenue ≥ 0
⭐ Power BI Data Model

The Power BI model follows a Star Schema.

                 Dim_Date
                    │
                    │
Dim_Channel ─── Fact_Marketing ─── Dim_Product
                    │
                    │
                Dim_Region
Fact Table
Fact_Marketing

The central fact table contains measurable marketing performance data:

Campaign_ID
Date
Impressions
Clicks
Conversions
Spend
Revenue
Dimension Tables
Dim_Date
Date
Year
Month
Month Name
Year Month
Dim_Channel
Marketing Channel
Dim_Region
Region
Dim_Product
Product
🧮 DAX Measures
Total Impressions
Total Impressions =
SUM(
    Fact_Marketing[Impressions]
)
Total Clicks
Total Clicks =
SUM(
    Fact_Marketing[Clicks]
)
Total Conversions
Total Conversions =
SUM(
    Fact_Marketing[Conversions]
)
Total Spend
Total Spend =
SUM(
    Fact_Marketing[Spend]
)
Total Revenue
Total Revenue =
SUM(
    Fact_Marketing[Revenue]
)
📈 CTR — Click-Through Rate
Formula
CTR = Clicks ÷ Impressions
DAX
CTR =
DIVIDE(
    [Total Clicks],
    [Total Impressions],
    0
)
Business Meaning

CTR measures the percentage of ad impressions that resulted in clicks.

For example:

1,000,000 Impressions
46,200 Clicks
CTR = 4.62%

A CTR of 4.62% means that approximately 4.62 out of every 100 impressions resulted in a click.

🔄 Conversion Rate
Formula
Conversion Rate =
Conversions ÷ Clicks
DAX
Conversion Rate =
DIVIDE(
    [Total Conversions],
    [Total Clicks],
    0
)
Business Meaning

Conversion Rate measures the percentage of clicks that resulted in conversions.

💰 ROI — Return on Investment
Formula
ROI =
(Revenue - Spend) ÷ Spend
DAX
ROI =
DIVIDE(
    [Total Revenue] - [Total Spend],
    [Total Spend],
    0
)
Business Meaning

ROI measures the profit generated compared with the marketing investment.

Example
Revenue = $500,000
Spend   = $100,000
ROI =
($500,000 - $100,000)
÷ $100,000
ROI = 400%

The DAX measure should be formatted as Percentage in Power BI.

💵 CPC — Cost Per Click
Formula
CPC =
Spend ÷ Clicks
DAX
CPC =
DIVIDE(
    [Total Spend],
    [Total Clicks],
    0
)

CPC measures the average cost of generating one click.

💳 CPA — Cost Per Acquisition
Formula
CPA =
Spend ÷ Conversions
DAX
CPA =
DIVIDE(
    [Total Spend],
    [Total Conversions],
    0
)

CPA measures the average marketing cost of generating one conversion.

📊 Power BI Dashboard
1️⃣ Executive Overview

The first page provides a high-level summary of overall marketing performance.

KPI Cards
Total Spend
Total Revenue
Total Conversions
CTR
ROI
Visualizations
Monthly Revenue Trend
Revenue by Marketing Channel
Conversions by Region
Slicers
Year
Region
Product
Marketing Channel
2️⃣ Channel & Campaign Performance

This page focuses on marketing channel and campaign efficiency.

Analysis
Marketing Spend by Channel
Revenue by Channel
CTR by Channel
Conversion Rate by Channel
Campaign Performance
Campaign Performance Table

The table includes:

Campaign ID
Total Spend
Total Revenue
Total Clicks
Total Conversions
CTR
Conversion Rate
ROI

This page helps identify the most effective marketing channels and campaigns.

3️⃣ Regional & Product Performance

This page analyzes performance across regions and products.

Visualizations
Revenue by Region
Revenue by Product
Conversions by Region
Conversions by Product
Product and Region Matrix
Slicers
Year
Region
Product
Marketing Channel

This page helps identify high-performing regions and products.

📌 Key Business Questions Answered

The dashboard supports analysis of:

Which channel generates the highest revenue?
Which channel has the highest CTR?
Which campaign generates the most conversions?
Which region performs best?
Which product generates the most revenue?
Which channel has the best ROI?
Which campaigns require optimization?
💡 Business Recommendations

Based on the analysis, marketing teams can:

Increase investment in high-performing marketing channels.
Reduce spending on low-performing campaigns.
Optimize campaigns with high CPC or CPA.
Focus on high-converting regions.
Promote high-performing products.
Monitor monthly revenue trends.
Use CTR, Conversion Rate, and ROI together to evaluate campaign effectiveness.
🛠️ Technologies Used
Technology	Purpose
Python	Data preparation and validation
Pandas	Data cleaning and transformation
NumPy	Numerical calculations
Power BI	Data visualization and reporting
DAX	Dynamic KPI calculations
Excel	Source data
CSV	Data exchange
🎓 Skills Demonstrated
Data Cleaning
Data Quality Validation
Exploratory Data Analysis
Python
Pandas
NumPy
Data Modeling
Star Schema
Power BI
DAX
KPI Development
Data Visualization
Business Analysis
Marketing Analytics
Interactive Reporting
