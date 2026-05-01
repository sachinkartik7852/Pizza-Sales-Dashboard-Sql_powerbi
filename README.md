Here is a **professional README.md file** created using your **SQL + Power BI Pizza Sales project**, following the same structured format as your previous example:

---

# 🍕 Pizza Sales Analysis – SQL & Power BI 

*Analyzing pizza sales data to uncover business insights, track KPIs, and build interactive dashboards using SQL and Power BI.*

---

## 📌 Table of Contents

* Overview
* Business Problem
* Dataset
* Tools & Technologies
* Project Structure
* Data Cleaning & Preparation
* Exploratory Data Analysis (EDA)
* SQL Analysis & Key Queries
* Dashboard
* How to Run This Project
* Final Recommendations
* Author & Contact

---

## 📊 Overview

This project focuses on analyzing pizza sales data to evaluate business performance and generate actionable insights.

* SQL → Data extraction & KPI calculations
* Power BI → Interactive dashboard & visualization

---

## 🧩 Business Problem

The goal of this project is to:

* Track overall revenue and sales performance
* Identify best and worst-selling pizzas
* Analyze customer ordering trends
* Evaluate product category and size performance
* Support data-driven business decisions

---

## 📂 Dataset

* Source: Pizza sales dataset
* Table used: `pizza_sales`
* Contains:

  * Order details
  * Pizza categories & sizes
  * Quantity and pricing

---

## 🛠 Tools & Technologies

* SQL (MySQL / SQL Server)
* Power BI (Dashboard Visualization)
* Excel / CSV (Data Source)

---

## 📁 Project Structure

```
pizza-sales-analysis/
│
├── README.md
├── pizza_sales.sql
├── pizza_sales_dataset.csv
│
├── dashboard/
│   └── pizza_sales_dashboard.pbix
│
├── queries/
│   └── pizza_kpi_queries.sql
```

---

## 🧹 Data Cleaning & Preparation

* Verified null and duplicate values
* Ensured correct data types
* Standardized date formats
* Removed inconsistent or invalid entries

---

## 📈 Exploratory Data Analysis (EDA)

### Key Observations:

* Total revenue generated from pizza sales
* Average order value identified
* High variation in pizza demand across categories

### Trends:

* Weekly and monthly sales patterns observed
* Certain days show higher order volumes

---

## 🧮 SQL Analysis & Key Queries

### 🔹 KPI Metrics

```sql
-- Total Revenue
SELECT SUM(total_price) AS Total_Revenue FROM pizza_sales;

-- Average Order Value
SELECT SUM(total_price) / COUNT(DISTINCT order_id) AS Avg_Order_Value FROM pizza_sales;

-- Total Orders
SELECT COUNT(DISTINCT order_id) AS Total_Orders FROM pizza_sales;

-- Total Pizzas Sold
SELECT SUM(quantity) AS Total_Pizza_Sold FROM pizza_sales;
```

---

### 🔹 Trends Analysis

```sql
-- Daily Trend
SELECT DATENAME(DW, order_date) AS order_day,
COUNT(DISTINCT order_id) AS total_orders
FROM pizza_sales
GROUP BY DATENAME(DW, order_date);

-- Monthly Trend
SELECT DATENAME(MONTH, order_date) AS Month_Name,
COUNT(DISTINCT order_id) AS Total_Orders
FROM pizza_sales
GROUP BY DATENAME(MONTH, order_date);
```

---

### 🔹 Sales Distribution

```sql
-- % Sales by Category
SELECT pizza_category,
SUM(total_price) AS total_revenue,
SUM(total_price)*100 / (SELECT SUM(total_price) FROM pizza_sales) AS pct
FROM pizza_sales
GROUP BY pizza_category;

-- % Sales by Size
SELECT pizza_size,
SUM(total_price) AS total_revenue,
SUM(total_price)*100 / (SELECT SUM(total_price) FROM pizza_sales) AS pct
FROM pizza_sales
GROUP BY pizza_size;
```

---

### 🔹 Performance Analysis

```sql
-- Top 5 Pizzas by Revenue
SELECT TOP 5 pizza_name, SUM(total_price) AS Total_Revenue
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Revenue DESC;

-- Bottom 5 Pizzas by Revenue
SELECT TOP 5 pizza_name, SUM(total_price) AS Total_Revenue
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Revenue ASC;
```

---

## 📊 Dashboard

Power BI dashboard includes:

* Revenue KPIs
* Daily & Monthly Trends
* Category & Size Distribution
* Top & Bottom Performing Pizzas

📌 Provides interactive filters and visual insights for decision-making

---

## ▶️ How to Run This Project

1. Load dataset into SQL database
2. Run SQL queries from `pizza_kpi_queries.sql`
3. Export results if needed
4. Open Power BI file:

```
dashboard/pizza_sales_dashboard.pbix
```

5. Connect to dataset and refresh visuals

---

## 📌 Final Recommendations

* Focus marketing on top-performing pizzas
* Improve or remove low-performing products
* Optimize pricing strategy for different sizes
* Increase promotions during low-sales days
* Monitor seasonal demand patterns

---

## 👤 Author & Contact

SACHIN KUMAR
Data Analyst

sachinkartik01@gmail.com
www.linkedin.com/in/
sachin-kumar-3622012b2
Vanity URL name

