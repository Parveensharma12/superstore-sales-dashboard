# 📊 Superstore Sales Dashboard

An interactive sales analysis dashboard built using **SQL (MySQL)** for data querying and **Excel (Pivot Tables + Slicers)** for visualization. This project analyzes retail sales data to uncover trends across categories, regions, customers, and time.

![Dashboard Preview](https://github.com/Parveensharma12/superstore-sales-dashboard/blob/main/Screenshot%202026-09-23%20143408.png)

---

## 🎯 Project Overview

This project takes a raw retail sales dataset and turns it into a fully interactive dashboard, combining:
- **SQL** for data cleaning, aggregation, and analysis (including subqueries)
- **Excel** for building Pivot Tables, Pivot Charts, and a connected, slicer-driven dashboard

The goal was to practice real-world data analyst workflows — importing data, writing analytical SQL queries, and presenting the results visually in a way a business stakeholder could actually use.

---

## 🗂️ Dataset

**Source:** Superstore Sales Dataset
**Size:** ~9,800 order line items (2015–2018)
**Fields:** Order ID, Order Date, Ship Date, Ship Mode, Customer Name, Segment, Region, Category, Sub-Category, Product Name, Sales

---

## 🛠️ Tools & Skills Used

| Tool | Purpose |
|---|---|
| **MySQL** | Data import, cleaning (date formatting), and analysis |
| **SQL Concepts** | `GROUP BY`, `ORDER BY`, `HAVING`, `JOIN`, Subqueries, Aggregate functions |
| **Excel** | Pivot Tables, Pivot Charts, Slicers, KPI Cards, Dashboard design |

---

## 🔍 SQL Analysis

All queries used for this analysis are available in [`queries.sql`](queries.sql), including:

1. Category-wise total sales
2. Month-wise sales trend
3. Region-wise sales
4. Top 10 customers by sales
5. Orders priced above the average sale (via subquery)
6. Sub-category performance

---

## 📈 Dashboard Features

The final Excel dashboard (`Superstore_Dashboard.xlsx`) includes:

- **4 KPI Cards** — Total Sales, Total Orders, Average Order Value, Top Category
- **6 interactive charts** — Category sales, Monthly trend, Region sales, Top 10 customers, Segment sales, Ship mode distribution
- **Slicers** for Region and Category, connected to every chart and KPI card for real-time filtering
- Custom dark-themed design for a clean, professional look

---

## 💡 Key Insights

| Metric | Value |
|---|---|
| Total Sales | $2.26M |
| Total Orders | 4,922 |
| Average Order Value | $231 |
| Top-Selling Category | Technology |

*(Update this table with your final, verified numbers before publishing.)*

---

## 📁 Files in This Repository

| File | Description |
|---|---|
| `Superstore_Dashboard.xlsx` | Complete interactive Excel dashboard with all Pivot Tables and charts |
| `queries.sql` | All SQL queries used for analysis, with sample outputs |
| `dashboard_screenshot.png` | Preview image of the final dashboard |
| `train.csv` | Raw dataset used for the analysis *(optional)* |

---

## 🚀 How to Use

1. Download `Superstore_Dashboard.xlsx`
2. Open the **Dashboard** sheet
3. Use the Region and Category slicers at the top to filter the entire dashboard interactively

---

## 👤 About This Project

Built as a hands-on learning project while transitioning from an audit role into data analytics — applying SQL and Excel skills to a real dataset from data import through to a finished, interactive dashboard.
