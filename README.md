# Task 4: SQL Data Analysis on Sales Data

## 📁 Dataset
- `sales_data.csv`  
- Imported into SQLite as a table named `sales`

## 🛠 Tools Used
- DB Browser for SQLite (for database import and query execution)

## 📊 Objective
To analyze the sales dataset using SQL by applying data manipulation, aggregation, filtering, and optimization techniques.

---

## ✅ SQL Tasks Completed

### 1. Preview the Data
Displayed the first 10 rows using:
```sql
SELECT * FROM sales LIMIT 10;
2. Total Sales by Region
Calculated the total sales per region:

sql
Copy
Edit
SELECT Region, SUM(Sales_Amount) AS Total_Sales
FROM sales
GROUP BY Region
ORDER BY Total_Sales DESC;
3. Average Unit Price per Product Category
Computed the average unit price across categories:

sql
Copy
Edit
SELECT Product_Category, AVG(Unit_Price) AS Avg_Unit_Price
FROM sales
GROUP BY Product_Category
ORDER BY Avg_Unit_Price DESC;
4. Top Performing Sales Representatives
Identified the top 5 sales reps by total sales:

sql
Copy
Edit
SELECT Sales_Rep, SUM(Sales_Amount) AS Total_Sales
FROM sales
GROUP BY Sales_Rep
ORDER BY Total_Sales DESC
LIMIT 5;
5. Average Discount by Region
Measured the average discount across different regions:

sql
Copy
Edit
SELECT Region, AVG(Discount) AS Avg_Discount
FROM sales
GROUP BY Region
ORDER BY Avg_Discount DESC;
6. Sales Above Average (Subquery)
Filtered sales transactions that exceeded the average sale value:

sql
Copy
Edit
SELECT * FROM sales
WHERE Sales_Amount > (SELECT AVG(Sales_Amount) FROM sales);
7. Total Quantity Sold by Product Category
Summed total units sold per product category:

sql
Copy
Edit
SELECT Product_Category, SUM(Quantity_Sold) AS Total_Units_Sold
FROM sales
GROUP BY Product_Category
ORDER BY Total_Units_Sold DESC;
8. Create a View for High-Value Sales
Created a view to highlight sales greater than ₹10,000:

sql
Copy
Edit
CREATE VIEW high_value_sales AS
SELECT *
FROM sales
WHERE Sales_Amount > 10000;
9. Indexing for Optimization
Created indexes to improve query performance:

sql
Copy
Edit
CREATE INDEX idx_sales_rep ON sales(Sales_Rep);
CREATE INDEX idx_region ON sales(Region);
CREATE INDEX idx_product_category ON sales(Product_Category);
10. Sales by Payment Method and Channel
Analyzed sales across payment methods and channels:

sql
Copy
Edit
SELECT Payment_Method, Sales_Channel, SUM(Sales_Amount) AS Total_Sales
FROM sales
GROUP BY Payment_Method, Sales_Channel
ORDER BY Total_Sales DESC;
