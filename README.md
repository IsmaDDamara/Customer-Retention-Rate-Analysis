# 📊 Customer Retention Rate Analysis

## 📌 Background

In a competitive retail landscape, **customer retention rate** is a key metric to evaluate the effectiveness of marketing and customer service strategies. Retaining existing customers is more cost-effective and profitable than acquiring new ones. However, many businesses face declining retention, leading to a higher **churn rate** and reduced revenue. Therefore, a data-driven approach is essential to understand customer behavior and design effective retention strategies.

## 🎯 Project Objectives

This project aims to:

* Calculate customer retention rate periodically based on available transaction data.
* Identify key factors that influence customer loyalty and purchasing behavior.
* Analyze customer cohorts to observe retention patterns over specific time periods.
* Provide strategic business insights to improve customer retention and reduce churn rate.
* Deliver interactive visualizations to facilitate monitoring of customer retention performance over time.

## 🧭 Analysis Steps

The following steps are performed in this project:

1. **Data Preparation & Cleaning**

   * Convert `order_date` to datetime and add a `year_month` column.
   * Remove missing values in `customer_id` and `product_name`, and filter out test products (e.g., containing “test”).
   * Add an `order_status` column to identify cancellations.
   * Normalize `quantity` values (must be positive) and remove negative prices.
   * Create a new column `amount = quantity × price`.
   * Standardize product names using `product_code`.
   * Convert `customer_id` to string and remove commas.
   * Remove outliers from `quantity` and `amount` using Z-score.

2. **Retention Data Transformation**

   * Calculate the number of orders per customer per month.
   * Determine each customer's first purchase month as their **cohort**.
   * Calculate the difference in months between transaction and cohort (`period_num`).
   * Create a cohort pivot table (rows: cohort month, columns: period number, values: number of unique customers).

3. **Retention Rate Calculation**

   * Compute retention rate as:
     `retention rate = number of customers in month-n ÷ number in cohort month`.
   * Visualize retention and churn trends per cohort and in aggregate.

## 📈 Dashboard
👉 [Lihat Dashboard](https://lookerstudio.google.com/s/n8j-5g6Qxac)

## ▶️ How to Run

Clone this repository:

```bash
git clone https://github.com/IsmaDDamara/Customer-Retention-Rate-Analysis.git
cd notebook
```

Run the analysis:

```bash
jupyter notebook retentionRate_analysis.ipynb
```
