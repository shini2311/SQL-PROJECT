<h1 style="font-size:42px; text-align:left; font-weight:700;">
Retail Sales Analysis – SQL Project
</h1>
<h2 style="font-size:42px;">
  Project Overview 
</h2>
<b> Project Title: </b> Retail sales Analysis 

<b> Database: </b> Kaggle

This project analyzes the retail sales dataset provided by the client using SQL. The data was cleaned, structured, and transformed to ensure accuracy and consistency. Key SQL queries were used to identify sales trends, customer behavior, and product performance. The insights support better decision-making in inventory planning, marketing, and branch operations. Overall, the project delivers a clear data-driven view of business performance.

<h2> Objectives</h2>

<b>Data Cleaning:</b> Identify and remove any records with missing or null values.

<b0>Exploratory Data Analysis (EDA):</b> Perform basic exploratory data analysis to understand the dataset.

<b>Business Analysis:</b> Use SQL to answer specific business questions and derive insights from the sales data.

<h2 style="font-size:42px;">
  Project Structure
</h2>
<h3> 1. Database Setup</h3>
The project starts by creating a database named sales.

A table named retail_sales_data is created to store the sales data.The table structure includes columns for transactions ID, sale date, sale time, customer ID, gender, age, product category, quantity sold, price per unit, cost of goods sold (COGS), and total sale amount.

```
CREATE DATABASE sales;

CREATE TABLE retail_sales_data
(
   transactions_id int PRIMARY KEY,
   sale_date date,	
   sale_time time,
   customer_id	int,
   gender varchar(20),
   age int,
   category varchar(20),	
   quantity	 int,
   price_per_unit float,	
   cogs	float,
   total_sale float
	);
```
<h3>2. Data Exploration & Cleaning</h3>

<b>Record Count:</b> Determine the total number of records in the dataset.

<b>Customer Count:</b> Find out how many unique customers are in the dataset.

<b>Category Count:</b> Identify all unique product categories in the dataset.

<b>Null Value Check:</b> Check for any null values in the dataset and delete records with missing data.

```
SELECT  SUM(transactions_id)  FROM retail_sales_data;
```

```
SELECT COUNT(*) FROM retail_sales_data;
```
```
SELECT DISTINCT category FROM retail_sales_data;
```
```
SELECT * FROM retail_sales_data
WHERE 
    sale_date IS NULL OR sale_time IS NULL OR customer_id IS NULL OR 
    gender IS NULL OR age IS NULL OR category IS NULL OR 
    quantity IS NULL OR price_per_unit IS NULL OR cogs IS NULL;

DELETE FROM retail_sales_data
WHERE 
    sale_date IS NULL OR sale_time IS NULL OR customer_id IS NULL OR 
    gender IS NULL OR age IS NULL OR category IS NULL OR 
    quantity IS NULL OR price_per_unit IS NULL OR cogs IS NULL;
```

<h3>3. Data Analysis & Findings</h3>
