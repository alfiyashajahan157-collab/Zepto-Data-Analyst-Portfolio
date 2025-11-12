# Zepto-Data-Analyst-Portfolio
A complete SQL-based data analytics portfolio project using Zepto e-commerce data. This project demonstrates real-world data analysis skills — from raw data cleaning and exploration to generating business insights on sales, products, and customer behavior.
🛒 Zepto E-commerce SQL Data Analyst Portfolio Project

This project simulates how real data analysts in the e-commerce industry use SQL to explore, clean, and analyze inventory data.
It is built on a dataset inspired by Zepto, one of India’s fastest-growing quick-commerce startups.

📌 Project Overview

The goal is to demonstrate practical SQL skills by:

✅ Setting up a realistic e-commerce inventory database
✅ Performing Exploratory Data Analysis (EDA) on product categories, pricing, and availability
✅ Cleaning data (handling nulls, removing invalid entries, converting paise → ₹)
✅ Writing business-driven SQL queries for insights on pricing, stock, and revenue

📁 Dataset Overview

The dataset is sourced from Kaggle and mimics a real e-commerce inventory system.
Each record represents a product SKU (Stock Keeping Unit). Duplicate names occur for items sold in different package sizes, weights, or discounts — just like real-world catalog data.

🧾 Columns
Column	Description
sku_id	Unique identifier for each product
name	Product name
category	Product category (e.g., Fruits, Snacks, Beverages)
mrp	Maximum Retail Price (in ₹)
discountPercent	Discount applied on MRP
discountedSellingPrice	Final price after discount (₹)
availableQuantity	Units available in inventory
weightInGms	Product weight in grams
outOfStock	Boolean flag for stock availability
quantity	Units per package / loose produce quantity
🔧 Project Workflow
1️⃣ Database & Table Creation
CREATE TABLE zepto (
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);

2️⃣ Data Import

Import the CSV using pgAdmin or:

\copy zepto(category,name,mrp,discountPercent,availableQuantity,
            discountedSellingPrice,weightInGms,outOfStock,quantity)
FROM 'data/zepto_v2.csv'
WITH (FORMAT csv, HEADER true, DELIMITER ',', QUOTE '"', ENCODING 'UTF8');


If you face encoding errors, re-save the CSV as UTF-8.

3️⃣ 🔍 Data Exploration

Count total records

View sample rows

Check for nulls

List distinct categories

Compare in-stock vs out-of-stock counts

Identify duplicate product SKUs

4️⃣ 🧹 Data Cleaning

Remove rows with zero MRP or discounted price

Convert prices from paise to rupees

5️⃣ 📊 Business Insights

Top 10 best-value products (by discount %)

Out-of-stock high-MRP items

Potential revenue per category

Expensive products (MRP > ₹500) with low discounts

Top 5 categories by average discount

Price per gram for value analysis

Group products by weight (Low / Medium / Bulk)

Total inventory weight by category

🛠️ How to Use This Project
git clone https://github.com/<your-username>/Zepto-Ecommerce-SQL-Analysis.git
cd Zepto-Ecommerce-SQL-Analysis


Create a PostgreSQL database.

Run the SQL file zepto_SQL_data_analysis.sql.

Import the dataset (ensure UTF-8 encoding).

Execute the SQL queries step by step to reproduce analysis and insights.

📜 License

MIT License — free to use, fork, and showcase in your own portfolio.
