# 📊 Ecommerce SQL Analysis & Dashboard

## 📌 Introduction
This project analyzes an ecommerce dataset using SQL queries and visualizes the results in Looker Studio.  
The goal is to uncover insights about orders, customers, products, returns, and revenue trends, and present them in a professional dashboard.

## 🎯 Objectives
- Count total orders and customers
- Identify top products by quantity and revenue
- Analyze returns and their financial impact
- Explore revenue by country and monthly trends
- Calculate KPIs like Average Order Value (AOV)
- Build a dashboard to communicate insights visually

## 🛠️ Methods
- Queries were written in SQL and executed on a SQLite database.  
- Screenshots of queries and results are stored in the `/screenshots` folder.  
- A dashboard was built in Looker Studio using the dataset (CSV uploaded via Google Sheets).  
- Each query is documented with:
  - **Query purpose**
  - **SQL code**
  - **Result screenshot**
  - **Insight & recommendation**

## 📈 Results & Insights

### Orders & Customers
**Query:**
```sql
SELECT COUNT(invoiceno) AS total_orders,
       COUNT(DISTINCT customerid) AS unique_customers
FROM ecommerce;
```
Result: 541,909 orders from 4,373 unique customers
Insight: Strong engagement with a large customer base.
Future Purpose: Track monthly growth and retention rates.

Top Products by Revenue
Query:

```sql
SELECT description, SUM(revenue) AS total_revenue
FROM ecommerce
GROUP BY description
ORDER BY total_revenue DESC
LIMIT 10;
```
Result: High‑revenue products include “DOTCOM Postage” and “Regency Cake Stand.”
Insight: These items drive profitability.
Future Purpose: Focus marketing and inventory on top sellers.

Returns Analysis
Query:

```sql
SELECT description, SUM(quantity) AS total_unit_returned,
       SUM(revenue) AS total_return
FROM ecommerce
WHERE quantity < 0
GROUP BY description
ORDER BY total_unit_returned ASC
LIMIT 10;
```
Result: 16,624 return transactions worth nearly £900K.
Insight: Products like “Paper Craft Little Birdie” have very high return rates.
Future Purpose: Improve supplier quality and reduce defects.

Geographic Insights
Query:

```sql
SELECT country, COUNT(invoiceno) AS total_orders, SUM(revenue) AS total_revenue
FROM ecommerce
GROUP BY country
ORDER BY total_revenue DESC;
```
Result: UK dominates sales, followed by Germany and France.
Insight: Strong domestic market, but international growth potential.
Future Purpose: Target Germany and France with localized campaigns.

Monthly Revenue Trend
Query:

```sql
SELECT month, SUM(revenue) AS monthly_revenue
FROM ecommerce
GROUP BY month
ORDER BY month;
```
Result: Revenue peaks in November and December.
Insight: Seasonal demand around holidays.
Future Purpose: Plan inventory and promotions around Q4.

📊 Dashboard
The interactive dashboard built in Looker Studio visualizes:

KPIs: Orders, Customers, Products, Revenue, AOV

Product Performance: Top products by quantity and revenue

Customer Insights: Top customers by orders and revenue

Geographic Insights: Revenue by country, top countries by orders

Monthly Trends: Revenue distribution across months

![Dashboard Overview](E-Commerce_Dashboard)

You can view the live dashboard here: [View Dashboard](https://lookerstudio.google.com/reporting/7e1f72aa-1afe-4840-8854-9919fd83dad1)

✅ Recommendations
Focus marketing on high‑revenue products while monitoring margins

Improve supplier quality to reduce costly returns

Expand in Germany and France with targeted campaigns

Build loyalty programs for top customers to secure repeat sales

Plan inventory around Q4 peaks to maximize profit

🚀 Future Work
Customer segmentation for personalized marketing

Return rate analysis by customer and product category

Monthly growth forecasting and trend analysis
