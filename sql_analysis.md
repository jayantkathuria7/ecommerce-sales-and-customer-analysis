# SQL Analysis Report

This report presents SQL-driven insights on E-commerce sales and customer behavior. Each section includes the SQL query used, the resulting output (shown as an image), and a concise business insight.

---

## 1. Cities with the Highest Sales Share

**SQL Query:**
```sql
SELECT City, SUM(Sales) AS TotalSales
FROM ecommerce_data
GROUP BY City
ORDER BY TotalSales DESC
LIMIT 10;
````

![Cities with the highest sales share.png](sql-analysis/cities_with_the_highest_sales_share.png)

---

## 2. Number of Rows in the Dataset

**SQL Query:**

```sql
SELECT COUNT(*) FROM ecommerce_data;
```

![no\_of\_rows.png](sql-analysis/no_of_rows.png)

**Insight:**    

---

## 3. Null Values in Each Column

**SQL Query:**

```sql
SELECT 
  SUM(CASE WHEN column1 IS NULL THEN 1 ELSE 0 END) AS column1_nulls,
  SUM(CASE WHEN column2 IS NULL THEN 1 ELSE 0 END) AS column2_nulls,
  ...
FROM ecommerce_data;
```

![null values in each column.png](sql-analysis/null_values_in_each_column.png)

**Insight:**

---

## 4. Number of Unique Values in Each Column

**SQL Query:**

```sql
SELECT 
  COUNT(DISTINCT column1) AS column1_uniques,
  COUNT(DISTINCT column2) AS column2_uniques,
  ...
FROM ecommerce_data;
```

![number of unique values in each col.png](sql-analysis/number_of_unique_values_in_each_col.png)

**Insight:**

---

## 5. Original Dataset Preview

**SQL Query:**

```sql
SELECT * FROM ecommerce_data LIMIT 5;
```

![original\_dataset.png](sql-analysis/original_dataset.png)

**Insight:**

---

## 6. States with the Highest Sales Share

**SQL Query:**

```sql
SELECT State, SUM(Sales) AS TotalSales
FROM ecommerce_data
GROUP BY State
ORDER BY TotalSales DESC
LIMIT 10;
```

![States with  the highest sales share.png](sql-analysis/states_with_the_highest_sales_share.png)

**Insight:**

---

## 7. Top 10 Frequent Customers (Most Orders)

**SQL Query:**

```sql
SELECT Customer_Name, COUNT(*) AS OrderCount
FROM ecommerce_data
GROUP BY Customer_Name
ORDER BY OrderCount DESC
LIMIT 10;
```

![Top 10 frequent customers.png](sql-analysis/top_10_frequent_customers.png)

**Insight:**

---

## 8. Top 10 Highest Buying Customers (by Sales Amount)

**SQL Query:**

```sql
SELECT Customer_Name, SUM(Sales) AS TotalSales
FROM ecommerce_data
GROUP BY Customer_Name
ORDER BY TotalSales DESC
LIMIT 10;
```

![Top 10 highest buying customers.png](sql-analysis/top_10_highest_buying_customers.png)

**Insight:**

---

## 9. Top 10 Most Sold Products (by Frequency)

**SQL Query:**

```sql
SELECT Product_Name, COUNT(*) AS TimesSold
FROM ecommerce_data
GROUP BY Product_Name
ORDER BY TimesSold DESC
LIMIT 10;
```

![Top 10 most sold products(based on how many times its been sold).png](sql-analysis/top_10_most_sold_products(based_on_how_many_times_its_been_sold).png)

**Insight:**

---

## 10. Top Selling Category

**SQL Query:**

```sql
SELECT Category, SUM(Sales) AS TotalSales
FROM ecommerce_data
GROUP BY Category
ORDER BY TotalSales DESC;
```

![Top selling category.png](sql-analysis/top_selling_category.png)

**Insight:**

---

## 11. Total and Average Revenue and Profit

**SQL Query:**

```sql
SELECT 
  SUM(Sales) AS TotalSales,
  AVG(Sales) AS AverageSales,
  SUM(Profit) AS TotalProfit,
  AVG(Profit) AS AverageProfit
FROM ecommerce_data;
```

![Total and average revenue and profit .png](sql-analysis/total_and_average_revenue_and_profit.png)

**Insight:**

---

## 12. Total Sales and Profit by Ship Mode

**SQL Query:**

```sql
SELECT Ship_Mode, SUM(Sales) AS TotalSales, SUM(Profit) AS TotalProfit
FROM ecommerce_data
GROUP BY Ship_Mode;
```

![Total sales and profit grouped by Ship Mode.png](sql-analysis/total_sales_and_profit_grouped_by_ship_mode.png)

**Insight:**
