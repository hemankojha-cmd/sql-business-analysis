# 📊 SQL Business Analysis

## 🔍 Overview

Performed **business data analysis using SQL** on a Superstore dataset stored in SQLite.
Focused on extracting insights related to revenue, profitability, customer behavior, and growth trends.

---

## 🛠️ Tools

* SQL (SQLite)
* Python (query execution)
* Pandas (result display)

---

## 📁 Data

* Superstore dataset (synthetic)
* ~3,000 records
* Fields: Orders, Customers, Products, Sales, Profit, Region, Dates

---

## 📊 Key SQL Analysis

* **Revenue & Profit Analysis**

  ```sql id="a1"
  SELECT category, SUM(sales), SUM(profit)
  FROM orders
  GROUP BY category;
  ```

* **Top Profitable Products**

  ```sql id="a2"
  SELECT product_name, SUM(profit)
  FROM orders
  GROUP BY product_name
  ORDER BY SUM(profit) DESC
  LIMIT 5;
  ```

* **Monthly Sales Trend**

  ```sql id="a3"
  SELECT STRFTIME('%Y-%m', order_date), SUM(sales)
  FROM orders
  GROUP BY 1;
  ```

* **Region Performance**

  ```sql id="a4"
  SELECT region, SUM(sales), SUM(profit)
  FROM orders
  GROUP BY region;
  ```

* **Discount Impact**

  ```sql id="a5"
  SELECT discount, AVG(profit)
  FROM orders
  GROUP BY discount;
  ```

* **State Ranking (Window Function)**

  ```sql id="a6"
  SELECT state,
         RANK() OVER (ORDER BY SUM(sales) DESC) AS rank
  FROM orders
  GROUP BY state;
  ```

---

## 🧠 SQL Concepts Used

* Aggregations (`SUM`, `AVG`, `COUNT`)
* `GROUP BY`, `ORDER BY`
* `CASE WHEN`
* Common Table Expressions (CTE)
* Window Functions (`RANK()`)
* Date Functions (`STRFTIME`)

---

## ⚙️ Run the Project

```bash id="a7"
pip install pandas notebook
jupyter notebook
```

Open:

```
analysis.ipynb
```

---

## 📌 Key Insights

* Technology category drives highest revenue
* Higher discounts reduce profitability
* Sales vary significantly across regions
* Top customers contribute major share of revenue

---


