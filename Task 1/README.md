# Retail Sales Exploratory Data Analysis – Task 1

## 📊 Project Overview

This project performs an Exploratory Data Analysis (EDA) on retail/e-commerce sales data to identify sales patterns, customer behaviour trends, product performance, and actionable business insights.

Revenue is derived using:

**Revenue = Quantity × Price**

## 🎯 Objectives

* Analyze monthly and quarterly revenue trends
* Understand customer demographics
* Identify the best-selling products
* Analyze revenue by product category
* Examine relationships between numerical variables
* Compare customer order volume and average revenue
* Generate actionable business recommendations

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook

## 📁 Dataset

The dataset contains 1,000 retail/e-commerce records with information including:

* Product name
* Product category
* Customer ID
* Customer age
* Gender
* Order date
* Quantity
* Price

A derived `Revenue` column is calculated as:

`Revenue = quantity × price`

## 🔍 Analysis Performed

### 1. Data Inspection & Quality Checks

* Dataset shape and columns
* Data types
* Missing values
* Duplicate records
* Invalid quantities and prices
* Invalid dates
* Unique products, categories, and customers

### 2. Sales Trend Analysis

Monthly and quarterly revenue trends were analyzed to identify high- and low-performing periods.

The highest monthly revenue was recorded in **August 2024**, at approximately **₹79,070**.

The highest quarterly revenue occurred in **Q3 2024**, at approximately **₹206,333**.

### 3. Customer Demographics

Customer behaviour was analyzed using age-group and gender distributions.

The **56–65 age group** recorded the highest number of orders, with **197 orders**.

The gender distribution was almost evenly balanced:

* Male: 50.9%
* Female: 49.1%

### 4. Product Performance

The Top 10 best-selling products were identified based on total quantity sold.

**Smartphone** was the best-selling product, with approximately **159 units sold**.

### 5. Category Revenue Analysis

Revenue was compared across product categories.

**Electronics** generated the highest revenue at approximately **₹166,510**.

### 6. Correlation Analysis

A correlation heatmap was used to study relationships between age, quantity, price, and revenue.

The strongest positive correlation with Revenue was:

* Price: **0.70**
* Quantity: **0.60**

Age showed almost no linear relationship with Revenue (**0.02**).

### 7. Customer Value Analysis

Average revenue per order was compared across age groups.

The **46–55 age group** had the highest average revenue per order at approximately **₹819**, while the **56–65 age group** had the highest order volume.

This demonstrates that customer frequency and customer value are different measures.

## 💡 Key Business Insights

* Prepare inventory and marketing campaigns ahead of strong sales periods.
* Maintain adequate stock for high-volume products.
* Prioritize high-revenue product categories.
* Use age-based segmentation for targeted marketing.
* Use bundles and cross-selling to increase basket size.
* Manage high-volume products differently from high-value products.

## 📈 Visualizations

The analysis includes:

* Monthly Revenue Trend
* Quarterly Revenue Trend
* Customer Distribution by Age Group
* Customer Gender Distribution
* Top 10 Best-Selling Products
* Revenue by Product Category
* Correlation Matrix
* Average Revenue per Order by Age Group
* Product Quantity vs Total Revenue

## ✅ Conclusion

The analysis provides insights into retail sales performance, product demand, customer demographics, and revenue patterns.

These findings can support better:

* Inventory planning
* Product promotion
* Customer segmentation
* Seasonal marketing
* Basket-size growth

Overall, the project demonstrates how exploratory data analysis can be used to convert retail data into actionable business insights.

## 📌 Project Files

* `Task_1_Retail_Sales_EDA.ipynb` – Complete analysis and visualizations
* `synthetic_online_retail_data.csv` – Dataset used for the analysis
