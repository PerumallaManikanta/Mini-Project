# 📊 Sales Analytics Dashboard Using Power BI

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow?style=for-the-badge&logo=powerbi)
![Data Analytics](https://img.shields.io/badge/Data%20Analytics-Project-blue?style=for-the-badge)
![DAX](https://img.shields.io/badge/DAX-Measures-orange?style=for-the-badge)
![Project Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

---

# Project Introduction

The **Sales Analytics Dashboard** is an interactive Business Intelligence project developed using **Microsoft Power BI**.

The project analyzes retail and e-commerce sales data to understand sales performance, profitability, regional performance, category performance, monthly trends, sales representative performance, and the relationship between discounts and profit.

The objective is to transform raw transactional data into meaningful business insights through **data cleaning, data modeling, DAX calculations, exploratory data analysis, and interactive visualization**.

The dashboard provides management with a centralized view of key performance indicators and supports data-driven decision-making.

---

# Problem Statement

The organization has sales transactions across different regions, states, product categories, subcategories, and sales representatives.

Analyzing raw transactional data manually makes it difficult for management to quickly identify:

- High-performing and underperforming regions
- High-performing product categories
- Profitability across categories
- Monthly sales trends
- Sales representative performance
- The relationship between discounts and profit
- Areas where sales and profitability can be improved

Therefore, an interactive Power BI dashboard was developed to provide a clear and centralized view of sales and profitability performance.

---

# Business Objectives

The primary objectives of this project are:

1. Analyze overall sales performance.
2. Monitor total sales and total profit.
3. Calculate and analyze profit margin.
4. Track total orders.
5. Analyze monthly sales trends.
6. Compare sales and profit across regions.
7. Identify high-performing and underperforming regions.
8. Analyze category-level sales performance.
9. Analyze category-level profitability.
10. Evaluate sales representative performance.
11. Analyze discount versus profit.
12. Generate actionable business insights.
13. Provide business recommendations.
14. Support management with data-driven decisions.
15. Develop an interactive and user-friendly Power BI dashboard.

---

# Dataset Information

The project uses retail and e-commerce transaction data supported by dimension tables.

## Main Fact Table – Retail & E-commerce

| Column | Description |
|---|---|
| Order Id | Unique order identifier |
| Order Date | Date of transaction |
| Month | Month of transaction |
| Quarter | Quarter of transaction |
| Year | Year of transaction |
| Region | Geographical region |
| State | State of transaction |
| Category | Product category |
| Subcategory | Product subcategory |
| Sales | Revenue generated |
| Cost | Cost associated with the transaction |
| Profit | Profit generated |
| Discount | Discount applied |
| Sales Representative | Person responsible for the sale |
| Remarks | Additional transaction information |

## Category Table

| Column | Description |
|---|---|
| Category Id | Unique category identifier |
| Category | Product category |

## Subcategory Table

| Column | Description |
|---|---|
| Subcategory Id | Unique subcategory identifier |
| Subcategory | Product subcategory |

## Sales Representative Table

| Column | Description |
|---|---|
| Sales Representative Id | Unique sales representative identifier |
| Sales Representative | Sales representative name |

# DAX Measures

The following DAX measures were created for the dashboard.

## Total Sales

```DAX
Total Sales =
SUM('Retail & E-commerce'[Sales])
```

## Total Profit

```DAX
Total Profit =
SUM('Retail & E-commerce'[Profit])
```

## Total Orders

```DAX
Total Orders =
DISTINCTCOUNT('Retail & E-commerce'[Order Id])
```

## Profit Margin %

```DAX
Profit Margin % =
DIVIDE(
    [Total Profit],
    [Total Sales],
    0
)
```

### Formula

```text
Profit Margin % = (Total Profit / Total Sales) × 100
```

## Average Sales

```DAX
Average Sales =
AVERAGE('Retail & E-commerce'[Sales])
```

## Average Profit

```DAX
Average Profit =
AVERAGE('Retail & E-commerce'[Profit])
```

## Average Discount %

```DAX
Average Discount % =
AVERAGE('Retail & E-commerce'[Discount])
```

## Sales YTD

```DAX
Sales YTD =
TOTALYTD(
    [Total Sales],
    'Date Table'[Date]
)
```

## Profit YTD

```DAX
Profit YTD =
TOTALYTD(
    [Total Profit],
    'Date Table'[Date]
)
```

## Previous Year Sales

```DAX
Previous Year Sales =
CALCULATE(
    [Total Sales],
    SAMEPERIODLASTYEAR('Date Table'[Date])
)
```

## Sales Growth %

```DAX
Sales Growth % =
DIVIDE(
    [Total Sales] - [Previous Year Sales],
    [Previous Year Sales],
    0
)
```

> **Note:** The YTD and previous-year measures require a properly configured Date Table related to the Order Date.

---

# EDA

Exploratory Data Analysis was performed to identify trends, patterns, performance differences, and relationships within the sales data.

## Monthly Sales Analysis

The Monthly Sales Trend was analyzed to understand changes in sales over time.

The dashboard shows fluctuations in monthly sales, which can be investigated further for seasonal patterns and demand changes.

## Regional Analysis

Sales and profit were compared across:

- East
- West
- North
- South

The displayed analysis indicates that the **West region is one of the strongest performers**.

## Category Analysis

Sales were analyzed across the major product categories:

- Electronics
- Furniture
- Office Supplies

The dashboard indicates that **Electronics is the leading category by total sales**.

## Profitability Analysis

Profit margin was compared across categories to understand profitability relative to sales.

## Sales Representative Analysis

Sales representative performance was analyzed using total sales.

The dashboard shows differences in sales contributions across representatives.

## Discount vs Profit Analysis

A scatter chart was used to analyze the relationship between discount levels and profit.

This helps management evaluate whether higher discounts may affect profitability.

## Dashboard KPIs

The dashboard currently displays:

| KPI | Value |
|---|---:|
| Total Sales | **15.42M** |
| Total Profit | **4.67M** |
| Profit Margin | **30.26%** |
| Total Orders | **1K** |

> KPI values may change when Year, Quarter, or Region filters are applied.

---

# Key Insights

### 1. Strong Overall Sales Performance

The business generated approximately **15.42M in Total Sales**, indicating strong revenue performance during the analyzed period.

### 2. Healthy Profitability

The business generated approximately **4.67M in Total Profit**.

### 3. Strong Profit Margin

The overall **Profit Margin is 30.26%**, showing a healthy level of profitability in the displayed dashboard.

### 4. Regional Performance Differences

Sales and profit vary across regions.

The **West region appears to be one of the strongest performers** in the displayed analysis.

### 5. Electronics Is the Leading Category

**Electronics generates the highest total sales** among the displayed categories.

### 6. Category Profitability

The category-level profit margin comparison helps management evaluate both sales contribution and profitability.

### 7. Sales Representative Performance Varies

Sales contribution differs among sales representatives.

This creates opportunities for performance benchmarking, training, and sharing successful sales practices.

### 8. Monthly Sales Fluctuate

Sales vary across months, indicating opportunities to investigate seasonal demand and plan inventory and marketing activities accordingly.

### 9. Discount and Profit Relationship

The Discount vs Profit visualization shows variation in profit at different discount levels.

Discount strategies should therefore be monitored carefully.

### 10. Unknown Sales Representative Records

An **Unknown** Sales Representative value appears in the dashboard.

This indicates that some transactions may have incomplete or unmatched sales representative information and should be reviewed in the source data.

---

# Business Recommendations

## 1. Strengthen Underperforming Regions

Analyze the reasons behind lower regional performance and improve:

- Sales coverage
- Marketing activities
- Product availability
- Customer engagement

## 2. Focus on High-Performing Categories

Since Electronics is a major sales contributor, management should ensure:

- Adequate inventory
- Product availability
- Effective promotions
- Competitive pricing

## 3. Optimize Discount Strategy

Monitor discount levels carefully to ensure that additional sales do not reduce profitability unnecessarily.

## 4. Improve Sales Representative Performance

Study the practices of high-performing representatives and provide additional training and support to lower-performing representatives.

## 5. Resolve Unknown Sales Representative Records

Review the source data and correctly map transactions currently classified as **Unknown**.

## 6. Monitor Monthly Trends

Use monthly sales patterns to support:

- Inventory planning
- Marketing planning
- Promotional campaigns
- Sales target setting

## 7. Balance Sales and Profitability

Management should not focus only on sales volume. Both **sales and profit margin** should be considered when making business decisions.

---

# Business Impact

The dashboard can support the organization in the following areas:

### Sales Management

Identify high-performing and underperforming regions and product categories.

### Profitability Management

Monitor total profit and profit margin to identify opportunities for improvement.

### Regional Strategy

Compare regional performance and allocate resources more effectively.

### Sales Team Management

Monitor sales representative performance and identify training opportunities.

### Discount Management

Analyze discounts alongside profit to support better promotional decisions.

### Management Reporting

Provide a centralized and interactive reporting solution instead of relying on manual analysis.

### Data-Driven Decision Making

Enable management to make faster and more informed decisions using visual business insights.

---

# Limitations

The current project has the following limitations:

1. Dashboard accuracy depends on source-data quality.
2. Some sales representative records may be missing or unmatched.
3. Customer-level information is not available.
4. Inventory information is not included.
5. Competitor information is not available.
6. External market factors are not included.
7. Predictive analytics has not been implemented.
8. The project primarily focuses on descriptive and diagnostic analysis.
9. Detailed customer behavior cannot be analyzed without customer-level data.
10. Discount analysis can be enhanced further using weighted discount calculations.

---

# Future Scope

The project can be enhanced with the following features.

## Sales Forecasting

Implement predictive models to forecast future sales and profit.

## Customer Analytics

Add customer-level data to analyze:

- Customer segmentation
- Customer retention
- Customer lifetime value
- Repeat purchases

## Inventory Analytics

Add inventory information to analyze:

- Stock levels
- Stock-outs
- Reorder levels
- Inventory turnover

## Geographic Analysis

Add map-based visualizations for state-level and regional performance.

## Advanced Discount Analysis

Develop:

- Weighted discount measures
- Discount impact on profit
- Discount versus sales growth
- Optimal discount analysis

## Predictive Analytics

Integrate Python or machine learning for:

- Sales forecasting
- Profit prediction
- Customer segmentation
- Anomaly detection

---

# Conclusion

The **Sales Analytics Dashboard** successfully transforms raw retail and e-commerce transaction data into an interactive Business Intelligence solution using **Microsoft Power BI**.

The project follows a complete analytics workflow:

```text
Raw Data
    ↓
Data Cleaning
    ↓
Data Transformation
    ↓
Data Modeling
    ↓
DAX Measures
    ↓
Exploratory Data Analysis
    ↓
Data Visualization
    ↓
Key Insights
    ↓
Business Recommendations
```

The dashboard provides management with a clear view of important business KPIs:

- **15.42M Total Sales**
- **4.67M Total Profit**
- **30.26% Profit Margin**
- **Approximately 1K Total Orders**

The analysis highlights regional performance differences, category-level sales, monthly sales trends, sales representative performance, and the relationship between discounts and profit.

Overall, this project demonstrates how raw business data can be transformed into meaningful insights and actionable recommendations that support better sales, profitability, and management decisions.

---

# Skills Demonstrated

- Microsoft Power BI
- Power Query
- DAX
- Data Cleaning
- Data Transformation
- Data Modeling
- Star Schema
- Exploratory Data Analysis
- KPI Development
- Data Visualization
- Business Intelligence
- Business Analysis
- Business Storytelling
- Insight Generation
- Data-Driven Decision Making

---

# 👨‍💻 Author

## Manikanta

**Aspiring Data Analyst | Power BI | Data Analytics | Business Intelligence**

### Project

**Sales Analytics Dashboard Using Power BI**

### Domain

**Retail & E-commerce**

### Project Type

**Data Analytics Mini Project / Portfolio Project**

### Primary Tool

**Microsoft Power BI**

### Project Status

**Completed ✅**

---

# ⭐ Final Project Statement

> **This project demonstrates my ability to transform raw retail sales data into an interactive Power BI dashboard, perform data cleaning and modeling, create DAX measures, conduct exploratory data analysis, generate actionable business insights, and provide data-driven recommendations.**

---
