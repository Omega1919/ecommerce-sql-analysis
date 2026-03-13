# 📊 Ecommerce SQL Analysis

## 📌 Introduction
This project explores an ecommerce dataset using SQL queries.  
The goal is to uncover insights about orders, customers, products, returns, and revenue trends.  
All queries were executed in SQLite, and screenshots of queries/results are included.

## 🎯 Objectives
- Count total orders and customers
- Identify top products by quantity and revenue
- Analyze returns and their financial impact
- Explore revenue by country and monthly trends
- Calculate KPIs like Average Order Value (AOV)

## 🛠️ Methods
Queries were written in SQL and executed on a SQLite database.  
Screenshots of queries and results are stored in the `/screenshots` folder.  
Each query is documented with:
- **Query purpose**
- **SQL code**
- **Result screenshot**
- **Insight & recommendation**

## 📈 Results & Insights
### Example: Total Orders
**Query:**
```sql
SELECT COUNT(invoiceno) FROM ecommerce;
