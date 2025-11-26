<h1 style="font-size:42px; text-align:left; font-weight:700;">
Retail Sales Analysis – SQL Project
</h1>
<h2>1. Project Overview</h2>

This project focuses on analyzing the retail sales data provided by the client to uncover meaningful business insights. Using SQL, the raw transaction data was cleaned, structured, and evaluated to understand customer behavior, product performance, revenue patterns, and operational efficiency. The analysis supports data-driven decision-making across sales, marketing, and inventory management.

<h2>2. Objective</h2>

<ol>
  
  • To analyze the sales transactions and understand key performance drivers.

  • To identify trends in customer demographics, product demand, and purchase behavior.

  • To help the client improve sales strategy, stocking decisions, and marketing targeting.

  • To deliver actionable insights using SQL-based analysis.
  
</ol>

<h2>3. Data Summary</h2>

The dataset contained 2,000 retail transactions with the following fields:
<ol>
  
• transactions_id

• sale_date, sale_time

• customer_id, gender, age

• category (product category)

• quantiy

• price_per_unit

• cogs

• total_sale
</ol>


The data showed good consistency with minimal missing values (only 3 missing in total_sale).

<h2>4. SQL Tasks Completed</h2>

<h3>4.1 Data Cleaning</h3>

<ol>

  • Handled missing values

  • Verified numeric formats (quantity, price, cogs, total_sale)

  • Standardized date and time fields
</ol>


<h3>4.2 Data Transformation</h3>

<ol>

 • Created computed fields (revenue by category, age group segmentation)

 • Extracted day, month, hour from sale_date and sale_time

 • Aggregated transactions for business KPIs
</ol>


<h3>4.3 Analysis Queries</h3>



<ol>

 • Total revenue, average order values, and category-wise performance

 • Customer demographic insights (gender & age patterns)

 • Peak shopping hours and popular purchase days

 • High-value customers identification

 • Pricing and quantity patterns
</ol>


<h2>5. Key Insights from the Analysis</h2>


<b> Based on the SQL analysis and dataset evaluation, the following insights were identified:</b>

1️⃣ Strongest Performing Product Categories

     • Clothing and Beauty were among the top-selling categories by quantity and revenue.

     • High-value items (500–2000 per unit) drove significant revenue.

2️⃣ Customer Demographics

     • Sales are balanced between males and females, with no extreme skew.

     • Majority of customers fall in the 25–50 age group, indicating a working-age buyer segment.

3️⃣ Revenue Trends

      • Average revenue per transaction: ₹456

      • High-variation revenue (min ₹25 to max ₹2000) indicates multiple pricing tiers.

4️⃣ Purchase Patterns

      • Most purchases involve 3–4 units per transaction.

      • Many high-value purchases are clustered around specific hours (morning + evening).

5️⃣ Cost & Margin Behaviour

      • COGS values vary significantly, pointing to mixed product margins.

      • Pricing strategy appears diversified across categories.


<h2>6. Business Impact & How It Helps the Client</h2>

1️⃣ Inventory Planning

<ol>Identifies top-selling categories and average quantity per purchase, helping in optimal stock levels.
</ol>
2️⃣ Marketing Strategy

Demographic insights allow targeted campaigns (age groups, gender trends).

3️⃣ Operational Improvements

Peak hour analysis supports better staffing and scheduling.

4️⃣ Revenue Growth

Understanding high-revenue categories guides product prioritization and promotions.

5️⃣ Customer Insights

Identifying repeat purchase behavior and high-value customers helps retention strategies.

<h2>7. Recommendations</h2>
<ol>

  • Increase stock levels for high-demand categories like Clothing & Beauty.

  • Run targeted promotions for the 25–50 age group.

  • Adjust staff allocation during peak shopping hours.

  • Review pricing strategy for categories with low margins.

  • Introduce loyalty programs to improve customer retention.
  
</ol>



<h2>8. Conclusion</h2>

This SQL-based retail sales analysis provides a clear view of customer behavior, product demand, and revenue trends. The insights identified from the dataset support strategic planning across inventory, marketing, and operations. The client can use these findings to improve business efficiency and drive long-term growth.

