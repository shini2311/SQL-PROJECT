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

<b>Exploratory Data Analysis (EDA):</b> Perform basic exploratory data analysis to understand the dataset.

<b>Business Analysis:</b> Use SQL to answer specific business questions and derive insights from the sales data.

<h2 style="font-size:42px;">
  Project Structure
</h2>
<h3> 1. Database Setup</h3>
<b>• Database Creation</b>The project starts by creating a database named sales.

<b>• Table Creation</b>A table named retail_sales_data is created to store the sales data.The table structure includes columns for transactions ID, sale date, sale time, customer ID, gender, age, product category, quantity sold, price per unit, cost of goods sold (COGS), and total sale amount.

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

<b>• Record Count:</b> Determine the total number of records in the dataset.

<b>• Customer Count:</b> Find out how many unique customers are in the dataset.

<b>• Category Count:</b> Identify all unique product categories in the dataset.

<b>•Null Value Check:</b> Check for any null values in the dataset and delete records with missing data.

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

<b>1. A SQL query to calculate the total sales (total_sale) for each category</b>
```
SELECT 
    category,
    SUM(total_sale) as Total_Sales,
    COUNT(*) as Total_Orders
FROM retail_sales_data
GROUP BY category;
```

<b>2. A SQL query to find the average age of customers who purchased items from the 'Beauty' category</b>

```
SELECT category, avg(age) FROM retail_sales_data WHERE category='Beauty';
<b> Write a SQL query to find all transactions where the total_sale is greater than 1000.
SELECT * FROM retail_sales_data WHERE total_sale > 1000;
```

<b>3. A SQL query to find the total number of transactions (transaction_id) made by each gender in each category</b>
```
SELECT 
    category,
    gender,
    COUNT(*) as Total_Transactions
FROM retail_sales_data
GROUP 
    BY 
    category,
    gender
ORDER BY category
```
<b>4. A SQL query to find all transactions where the total_sale is greater than 1000.</b>
```
SELECT * FROM retail_sales_data WHERE total_sale > 1000;
```
<b>5. A SQL query to find the total number of transactions (transaction_id) made by each gender in each category.</b>
```
SELECT gender,category, SUM(transactions_id) AS TRANSACTION FROM retail_sales_data GROUP BY gender , category ORDER BY 1;

```
<b>6. A SQL query to find the top 5 customers based on the highest total sales  </b>
```
SELECT customer_id, SUM(total_sale) AS TOTAL_SALE FROM retail_sales_data  GROUP BY customer_id ORDER BY TOTAL_SALE DESC LIMIT 5;
```
<b>7. A SQL query to find the number of unique customers who purchased items from each category.</b>
```
SELECT category, COUNT(*) AS CUSTOMERS FROM retail_sales_data GROUP BY category;
```
<b>8. A  SQL query to create each shift and number of orders (Example Morning <=12, Afternoon Between 12 & 17, Evening >17) </b>
```
WITH hourly_sale AS (
SELECT *, CASE
        WHEN EXTRACT(HOUR FROM sale_time) < 12 THEN 'Morning'
        WHEN EXTRACT(HOUR FROM sale_time) BETWEEN 12 AND 17 THEN 'Afternoon'
        ELSE 'Evening'
    END as shift FROM retail_sales_data
)
SELECT shift,COUNT(*) as total_orders FROM hourly_sale GROUP BY shift;
```
<b>9. Which category has the highest total sales overall </b>
```
SELECT category,SUM(total_sale) AS TOTAL_SALES FROM retail_sales_data GROUP BY category ORDER BY TOTAL_SALES DESC;

```
<b>10. Which day of the week has the maximum number of transactions</b>
```
SELECT 
    DATE_FORMAT(sale_date, '%W') AS day_of_week,
    COUNT(*) AS transaction_count
FROM retail_sales_data
GROUP BY day_of_week
ORDER BY transaction_count DESC;
```

<h3> Findings</h3>
• Identified the best-selling categories and highest revenue products.

• Found the peak sales months, days, and times.

• Highlighted top customers based on total spending.

• Understood sales patterns across age, gender, and location.

•Improved skills in SQL querying, data cleaning, and data analysis.

• Generated insights useful for business planning and decision-making.
