# 📊 Sales Performance Analysis Using SQL and Exploratory Data Techniques

This project explores sales trends across time and geography using structured query language (SQL) and exploratory data analysis (EDA) techniques. It focuses on identifying high-revenue regions, understanding seasonal demand patterns, and evaluating performance over multiple years to inform strategic business decisions.

---

## 📁 Project File

- `sales-performance-sql-eda-analysis.pdf` – Detailed report including SQL queries, data aggregation, and business insights derived from sales data across country, state, and time dimensions.

---

## 🎯 Objective

To analyze retail sales data and uncover actionable insights by aggregating metrics like revenue and quantity over temporal (year, quarter, month) and geographic (country, state) dimensions. The analysis supports data-driven decision-making in sales strategy, marketing, and supply chain planning.

---

## 🛠️ Tools & Techniques

- **SQL** – Data extraction, joins, and multi-level aggregations
- **Dimensional Modeling** – Identifying and leveraging fact and dimension tables
- **EDA Principles** – Time-series and geographic revenue performance analysis
- **Business Analytics** – Generating actionable insights for revenue optimization

---

## 🔍 Key Components

### 📌 Dimensions and Measures
- **Dimensions**: `Country`, `StateOrProvince`, `Month`, `Quarter`, `Year`
- **Measures**: `Revenue`, `Quantity`, `Latitude`, `Longitude`

---

### 📌 Sample SQL Query
```sql
SELECT  
    b.Year,  
    b.Quarter,  
    b.Month,  
    c.Country,  
    c.StateOrProvince,  
    SUM(a.Revenue) AS Revenue,  
    SUM(a.Quantity) AS Quantity  
FROM  
    FactTable AS a  
JOIN  
    TimeDimension AS b ON a.DateId = b.DateId  
JOIN  
    StateOrProvince AS c ON c.StoreId = a.StoreID  
GROUP BY  
    b.Year, b.Quarter, b.Month, c.Country, c.StateOrProvince;
