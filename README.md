# ☕ Coffee Shop Sales Analysis Project

## 🎯 **Objective**
This project aims to **analyze the sales performance** of a coffee shop using **SQL** for data extraction and **Power BI** for visualization. The analysis focuses on understanding **sales trends**, **order patterns**, and **quantity sold** over time, along with specific insights into **store locations**, **product categories**, and **day-wise performance**.

## 📊 **Project Overview**
In this project, I:
- 📝 Walked through the data to understand its structure and content.
- 🗃️ Prepared raw data files and created a **SQL database**.
- 📥 Imported and cleaned the data to ensure **accuracy and consistency**.
- 🔍 Executed **SQL queries** to extract business-relevant insights.
- 📈 Developed dynamic and interactive **Power BI dashboards** to visualize key performance indicators (**KPIs**).

## 🔄 **Project Workflow**

### 1. 📂 **Data Walkthrough**
- **Objective:** Understand the dataset structure, identify key columns, and determine the necessary cleaning steps.
- **Process:** Reviewed data files, identified column types, and mapped out the relationships between different data tables.

### 2. 🛠️ **Raw Data File Preparation**
- **Objective:** Prepare data files for importing into the SQL database.
- **Process:** Ensured that the raw data files were properly formatted and structured for seamless import.

### 3. 🗄️ **Creating Database**
- **Objective:** Set up a **SQL database** to store and manage the coffee shop's sales data.
- **Process:** Created a database schema, including tables for **sales**, **orders**, **products**, and **locations**.

### 4. 📤 **Importing File**
- **Objective:** Import raw data files into the SQL database.
- **Process:** Imported data using SQL scripts, ensuring that all records were accurately loaded into the respective tables.

### 5. 🧹 **Cleaning Imported File**
- **Objective:** Clean the imported data to ensure **data quality**.
- **Process:** 
  - **Standardized formats** (date, time, text).
  - **Corrected data types** (e.g., dates, numbers, text).
  - **Renamed columns** for clarity.
  - **Removed duplicates** and handled missing values.
  - **Applied constraints** like **NOT NULL** to enforce data integrity.
  - **Eliminated anomalies** and **normalized data**.

### 6. 🔧 **Changing Data Types**
- **Objective:** Ensure that each column in the dataset has the correct data type.
- **Process:** Modified columns to the appropriate data types, such as converting text to dates or numbers, to facilitate accurate analysis.

### 7. 🔍 **Firing SQL Queries for Business Requirements**
- **Objective:** Extract insights by running **SQL queries** to calculate **KPIs**.
- **Process:** 
  - Calculated **total sales**, **orders**, and **quantities sold** on a monthly basis.
  - Analyzed **month-over-month (MoM) growth** and differences.
  - Segmented sales by **store location** and **product category**.

### 8. 💾 **Storing Results**
- **Objective:** Store the results of SQL queries for further analysis and visualization.
- **Process:** Saved query results into separate tables or views within the database for easy access during dashboard creation.

### 9. 📝 **Preparing SQL Documents**
- **Objective:** Document all SQL queries for transparency and reproducibility.
- **Process:** 
  - Created a comprehensive **SQL query document** detailing each query used in the analysis.
  - Included comments to explain the purpose and logic of each query.

## 📈 **KPI Requirements and Analysis**

### 1. 💵 **Total Sales Analysis**
- **Metrics:**
  - **Total sales** for each month.
  - **Month-over-month increase or decrease**.
  - **Difference** between the selected month and the previous month.

### 2. 🛒 **Total Orders Analysis**
- **Metrics:**
  - **Total number of orders** for each month.
  - **Month-over-month increase or decrease**.
  - **Difference** between the selected month and the previous month.

### 3. 📦 **Total Quantity Sold Analysis**
- **Metrics:**
  - **Total quantity sold** for each month.
  - **Month-over-month increase or decrease**.
  - **Difference** between the selected month and the previous month.

## 🛠️ **Visualization and Dashboard Requirements**

### 1. 📅 **Calendar Heat Map**
- **Objective:** Visualize **daily sales volume** on a calendar, with darker shades representing higher sales.
- **Features:** 
  - **Dynamic adjustment** based on the selected month.
  - **Tooltips** displaying detailed metrics (Sales, Orders, Quantity) on hover.

### 2. 📊 **Sales Analysis by Weekdays and Weekends**
- **Objective:** Compare sales performance between **weekdays and weekends**.
- **Insights:** Identify significant differences in **sales patterns**.

### 3. 🏢 **Sales Analysis by Store Location**
- **Objective:** Visualize sales by **store location** and analyze **MoM differences**.
- **Features:** 
  - Highlight **MoM sales increase or decrease**.
  - Provide **trend insights** for each store location.

### 4. 📈 **Daily Sales Analysis with Average Line**
- **Objective:** Display **daily sales** with an average line to identify exceptional sales days.
- **Features:** 
  - Bars exceeding or falling below the **average sales** highlighted.
  - Insights into **daily sales performance**.

### 5. 🛍️ **Sales Analysis by Product Category**
- **Objective:** Analyze sales performance across different **product categories**.
- **Insights:** Determine which categories contribute the most to overall sales.

### 6. 🥇 **Top 5 Products by Sales**
- **Objective:** Identify and display the **top 5 products** based on **sales volume**.
- **Features:** Quick visualization of the **best-performing products**.

## 📝 **SQL Query Document**
- **Query 1:** 🧹 **Data Cleaning**
  - **Standardized formats**, corrected data types, renamed columns, removed duplicates, handled missing values, enforced consistency, eliminated anomalies, normalized data.
```SQL
Create database Project_Coffee_Shop_Sale;

use Project_Coffee_Shop_Sale;

select Count(*) from coffee_shop_sale;

update coffee_shop_sale
set transaction_date = str_to_date(transaction_date, "%d-%m-%Y");

alter table coffee_shop_sale
modify column transaction_date Date;

alter table coffee_shop_sale
change column ï»¿transaction_id transaction_id int;

-- Modify column data types and names as part of data cleaning
alter table coffee_shop_sale
modify column transaction_id int not null,
modify column transaction_date date not null,
modify column transaction_time time not null,
modify column transaction_qty int not null,
modify column store_id int not null,
modify column store_location varchar(100) not null,
modify column product_id int not null,
modify column unit_price decimal(10, 2) not null,
modify column product_category varchar(50) not null,
modify column product_type varchar(50) not null,
modify column product_detail text not null;

describe coffee_shop_sale;
```
#### 📝 **Output:**
| **Field**            | **Datatype**       | **Null** | **Key** | **Default** |
|----------------------|---------------------|----------|---------|-------------|
| `transaction_id`     | `int`               | NO       |  `Primary Key`       |             |
| `transaction_date`   | `date`              | NO       |         |             |
| `transaction_time`   | `time`              | NO       |         |             |
| `transaction_qty`    | `int`               | NO       |         |             |
| `store_id`           | `int`               | NO       |         |             |
| `store_location`     | `varchar(100)`      | NO       |         |             |
| `product_id`         | `int`               | NO       |         |             |
| `unit_price`         | `decimal(10,2)`     | NO       |         |             |
| `product_category`   | `varchar(50)`       | NO       |         |             |
| `product_type`       | `varchar(50)`       | NO       |         |             |
| `product_detail`     | `text`              | NO       |         |             |

- **Query 2:** 📊 **MoM Growth and Difference for Sales**
```SQL
SELECT 
    Sale_Month,
    Total_Sales,
    LAG(Total_Sales) OVER (ORDER BY Sale_Month) AS Previous_Month_Sales,
    (Total_Sales - LAG(Total_Sales) OVER (ORDER BY Sale_Month)) AS MoM_Difference,
    ROUND(
        ((Total_Sales - LAG(Total_Sales) OVER (ORDER BY Sale_Month)) / 
        LAG(Total_Sales) OVER (ORDER BY Sale_Month)) * 100, 2
    ) AS MoM_Growth_Percentage,
    CONCAT(
        IF(ROUND(
            ((Total_Sales - LAG(Total_Sales) OVER (ORDER BY Sale_Month)) / 
            LAG(Total_Sales) OVER (ORDER BY Sale_Month)) * 100, 2) >= 0, '+ ', '- '),
        ROUND(
            ABS(
                (Total_Sales - LAG(Total_Sales) OVER (ORDER BY Sale_Month)) / 
                LAG(Total_Sales) OVER (ORDER BY Sale_Month) * 100
            ), 2
        ),
        '% | ',
        ROUND(
            ABS(Total_Sales - LAG(Total_Sales) OVER (ORDER BY Sale_Month)) / 1000, 2
        ),
        'K Vs LM'
    ) AS MoM_Formatted
FROM (
    SELECT 
        MONTH(transaction_date) AS Sale_Month, 
        SUM(transaction_qty * unit_price) AS Total_Sales
    FROM 
        coffee_shop_sale
    GROUP BY 
        Sale_Month
) AS Monthly_Sales;
```
#### 📝 **Output:**
| **Sale_Month** | **Total_Sales** | **Previous_Month_Sales** | **MoM_Difference** | **MoM_Growth_Percentage** | **MoM_Formatted**                  |
|----------------|-----------------|--------------------------|--------------------|---------------------------|-----------------------------------|
| 1              | 81,677.74       | null                     | null               | null                      | null                              |
| 2              | 76,145.19       | 81,677.74                | -5,532.55          | -6.77%                    | - 6.77% | 5.53K Vs LM              |
| 3              | 98,834.68       | 76,145.19                | 22,689.49          | 29.80%                    | + 29.80% | 22.69K Vs LM             |
| 4              | 118,941.08      | 98,834.68                | 20,106.40          | 20.34%                    | + 20.34% | 20.11K Vs LM             |
| 5              | 156,727.76      | 118,941.08               | 37,786.68          | 31.77%                    | + 31.77% | 37.79K Vs LM             |
| 6              | 166,485.88      | 156,727.76               | 9,758.12           | 6.23%                     | + 6.23% | 9.76K Vs LM              |

- **Query 3:** 📅 **Total Sales Monthly**
```SQL
select month(transaction_date) AS Monthly_sale,
		concat("$ ",round(sum(transaction_qty*unit_price), 0)) As Total_Sales
from coffee_shop_sale
group by Monthly_sale;
```
#### 📝 **Output:**
| **Monthly_Sale** | **Total_Sales** |
|------------------|-----------------|
| 1                | $ 81,678        |
| 2                | $ 76,145        |
| 3                | $ 98,835        |
| 4                | $ 118,941       |
| 5                | $ 156,728       |
| 6                | $ 166,486       |

- **Query 4:** 🛒 **Total Orders Monthly**
```SQL
select month(transaction_date) AS Monthly_sale,
		round(count(transaction_qty)) As Total_Orders
from coffee_shop_sale
group by Monthly_sale;
```
#### 📝 **Output:**
| **Monthly_Sale** | **Total_Orders** |
|------------------|------------------|
| 1                | 17,314           |
| 2                | 16,359           |
| 3                | 21,229           |
| 4                | 25,335           |
| 5                | 33,527           |
| 6                | 35,352           |

- **Query 5:** 📦 **Total Quantity Monthly**
```SQL
select month(transaction_date) AS Monthly_Qty,
		concat(round(sum(transaction_qty)/1000, 2), "K  Qty") As Total_Qty
from coffee_shop_sale
group by Monthly_Qty;
```
#### 📝 **Output:**
| **Monthly_Qty** | **Total_Qty** |
|-----------------|---------------|
| 1               | 24.87K Qty    |
| 2               | 23.55K Qty    |
| 3               | 30.41K Qty    |
| 4               | 36.47K Qty    |
| 5               | 48.23K Qty    |
| 6               | 50.94K Qty    |

- **Query 6:** 📈 **MoM Growth and Difference for Orders**
```SQL
SELECT 
    Monthly_sale,
    Total_Orders, LAG(Total_Orders) OVER (ORDER BY Monthly_sale) As Previous_Month_Orders,
    (Total_Orders-LAG(Total_Orders) OVER (ORDER BY Monthly_sale)) as MoM_Difference,
        ROUND(
        ((Total_Orders-LAG(Total_Orders) OVER (ORDER BY Monthly_sale)) / 
        LAG(Total_Orders) OVER (ORDER BY Monthly_sale)) * 100, 2
    ) AS MoM_Growth_Percentage_Orders,
    CONCAT(
        IFNULL(CONCAT(
            IF((Total_Orders - LAG(Total_Orders) OVER (ORDER BY Monthly_sale)) >= 0, '+ ', '- '),
            ROUND(
                ABS(
                    ((Total_Orders - LAG(Total_Orders) OVER (ORDER BY Monthly_sale)) / 
                    LAG(Total_Orders) OVER (ORDER BY Monthly_sale)) * 100
                ), 2
            ), '%'
        ), 'N/A'),
        ' | ',
        IFNULL(CONCAT(
            IF((Total_Orders - LAG(Total_Orders) OVER (ORDER BY Monthly_sale)) >= 0, '+ ', '- '),
            ROUND(ABS((Total_Orders - LAG(Total_Orders) OVER (ORDER BY Monthly_sale))), 2)
        ), 'N/A'),
        ' Orders Vs LM'
    ) AS MoM_Comparison
FROM (
    SELECT 
        MONTH(transaction_date) AS Monthly_sale,
        ROUND(COUNT(transaction_qty)) AS Total_Orders
    FROM 
        coffee_shop_sale
    GROUP BY 
        Monthly_sale
) AS Monthly_Orders;
```
#### 📝 **Output:**
| **Monthly_Sale** | **Total_Orders** | **Previous_Month_Orders** | **MoM_Difference** | **MoM_Growth_Percentage_Orders** | **MoM_Comparison**         |
|------------------|------------------|---------------------------|--------------------|---------------------------------|-----------------------------|
| 1                | 17,314           | N/A                       | N/A                | N/A                             | N/A | N/A Orders Vs LM        |
| 2                | 16,359           | 17,314                    | -955               | -5.52%                          | - 5.52% | - 955 Orders Vs LM      |
| 3                | 21,229           | 16,359                    | 4,870              | 29.77%                          | + 29.77% | + 4870 Orders Vs LM     |
| 4                | 25,335           | 21,229                    | 4,106              | 19.34%                          | + 19.34% | + 4106 Orders Vs LM     |
| 5                | 33,527           | 25,335                    | 8,192              | 32.33%                          | + 32.33% | + 8192 Orders Vs LM     |
| 6                | 35,352           | 33,527                    | 1,825              | 5.44%                           | + 5.44% | + 1825 Orders Vs LM      |

- **Query 7:** 🔄 **MoM Growth and Difference for Quantity Sold**
``` SQL
SELECT 
    MONTH(transaction_date) AS Monthly_Qty,
    CONCAT(ROUND(SUM(transaction_qty) / 1000, 2), 'K Qty') AS Total_Qty,
    LAG(SUM(transaction_qty)) OVER (ORDER BY MONTH(transaction_date)) AS Previous_Month_Qty,
    (SUM(transaction_qty) - LAG(SUM(transaction_qty)) OVER (ORDER BY MONTH(transaction_date))) AS MoM_Difference,
    ROUND(
        ((SUM(transaction_qty) - LAG(SUM(transaction_qty)) OVER (ORDER BY MONTH(transaction_date))) / 
        LAG(SUM(transaction_qty)) OVER (ORDER BY MONTH(transaction_date))) * 100, 2
    ) AS MoM_Growth_Percentage,
    CONCAT(
        IFNULL(CONCAT(
            IF((SUM(transaction_qty) - LAG(SUM(transaction_qty)) OVER (ORDER BY MONTH(transaction_date))) >= 0, '+ ', '- '),
            ROUND(
                ABS(
                    ((SUM(transaction_qty) - LAG(SUM(transaction_qty)) OVER (ORDER BY MONTH(transaction_date))) / 
                    LAG(SUM(transaction_qty)) OVER (ORDER BY MONTH(transaction_date))) * 100
                ), 2
            ), '%'
        ), 'N/A'),
        ' | ',
        IFNULL(CONCAT(
            IF((SUM(transaction_qty) - LAG(SUM(transaction_qty)) OVER (ORDER BY MONTH(transaction_date))) >= 0, '+ ', '- '),
            ROUND(ABS((SUM(transaction_qty) - LAG(SUM(transaction_qty)) OVER (ORDER BY MONTH(transaction_date)))) / 1000, 2)
        ), 'N/A'),
        'K Qty Vs LM'
    ) AS Mom_Formatted
FROM 
    coffee_shop_sale
GROUP BY 
    MONTH(transaction_date)
ORDER BY 
    MONTH(transaction_date);
```
#### 📝 **Output:**
| **Monthly_Qty** | **Total_Qty** | **Previous_Month_Qty** | **MoM_Difference** | **MoM_Growth_Percentage** | **MoM_Formatted**         |
|-----------------|---------------|------------------------|--------------------|---------------------------|---------------------------|
| 1               | 24.87K Qty     | N/A                    | N/A                | N/A                       | N/A | N/A K Qty Vs LM    |
| 2               | 23.55K Qty     | 24.87K Qty             | -1,320             | -5.31%                    | - 5.31% | - 1.32K Qty Vs LM |
| 3               | 30.41K Qty     | 23.55K Qty             | 6,856              | 29.11%                    | + 29.11% | + 6.86K Qty Vs LM |
| 4               | 36.47K Qty     | 30.41K Qty             | 6,063              | 19.94%                    | + 19.94% | + 6.06K Qty Vs LM |
| 5               | 48.23K Qty     | 36.47K Qty             | 11,764             | 32.26%                    | + 32.26% | + 11.76K Qty Vs LM |
| 6               | 50.94K Qty     | 48.23K Qty             | 2,709              | 5.62%                     | + 5.62% | + 2.71K Qty Vs LM  |

- **Query 8:** 🏢 **Sales by Store Location for March**
```SQL
select store_location, sum(transaction_qty*unit_price) as Total_Sale
from coffee_shop_sale
where month(transaction_date) = 3
group by store_location;
```
#### 📝 **Output:**
| **Store Location**  | **Total_Sale** |
|---------------------|----------------|
| Lower Manhattan     | $32,888.68     |
| Hell's Kitchen       | $33,110.57     |
| Astoria              | $32,835.43     |

- **Query 9:** 📅 **Calculate Daily Sales Matrix and Include Average Daily Sale**
```SQL
WITH DailySales AS (
    SELECT 
        DAY(transaction_date) AS Day,
        SUM(transaction_qty * unit_price) AS Total_Sale_Per_Day,
        SUM(transaction_qty) AS Total_Qty,
        COUNT(transaction_id) AS Total_Orders
    FROM coffee_shop_sale
    WHERE MONTH(transaction_date) = 3
    GROUP BY DAY(transaction_date)
),
MonthlyAvg AS (
    SELECT 
        AVG(Total_Sale_Per_Day) AS Avg_Sale_Per_Day
    FROM DailySales
)
-- Main query to include daily metrics, average sales, and classification
SELECT 
    Day,
    Total_Sale_Per_Day,
    Total_Qty,
    Total_Orders,
    (SELECT Avg_Sale_Per_Day FROM MonthlyAvg) AS Avg_Sale_Per_Day,
    CASE
        WHEN Total_Sale_Per_Day > (SELECT Avg_Sale_Per_Day FROM MonthlyAvg) THEN 'Above Average'
        WHEN Total_Sale_Per_Day < (SELECT Avg_Sale_Per_Day FROM MonthlyAvg) THEN 'Below Average'
        ELSE 'Average'
    END AS Sales_Comparison
FROM DailySales
ORDER BY Day;
```
#### 📝 **Output:**
| **Day** | **Total_Sale_Per_Day** | **Total_Qty** | **Total_Orders** | **Avg_Sale_Per_Day** | **Sales_Comparison** |
|---------|-------------------------|---------------|------------------|----------------------|-----------------------|
| 1       | $3,040.25               | 968           | 661              | $3,188.22            | Below Average         |
| 2       | $2,996.05               | 963           | 673              | $3,188.22            | Below Average         |
| 3       | $3,155.15               | 1010          | 710              | $3,188.22            | Below Average         |
| 4       | $2,781.90               | 897           | 624              | $3,188.22            | Below Average         |
| 5       | $2,945.30               | 952           | 675              | $3,188.22            | Below Average         |
| ...     | ...                     | ...           | ...              | ...           | ...                   |
| 30      | $2,932.82               | 917           | 639              | $3,188.22            | Below Average         |
| 31      | $2,888.08               | 886           | 615              | $3,188.22            | Below Average         |

- **Query 10:** 📆 **Weekend and Weekday Sales**
```SQL
WITH cte AS (
    SELECT 
        *,
        CASE
            WHEN WEEKDAY(transaction_date) IN (5, 6) THEN 'Weekend'
            ELSE 'Weekday'
        END AS Weekend_Weekday,
        MONTHNAME(transaction_date) AS Month_Name
    FROM coffee_shop_sale
),
-- Calculate total sales for Weekday and Weekend by Month
sales_summary AS (
    SELECT 
        Month_Name,
        Weekend_Weekday,
        SUM(transaction_qty * unit_price) AS Total_Sales
    FROM cte
    GROUP BY 
        Month_Name,
        Weekend_Weekday
),
-- Pivot the sales data to get Weekday and Weekend sales in separate columns
pivot_sales AS (
    SELECT
        Month_Name,
        COALESCE(SUM(CASE WHEN Weekend_Weekday = 'Weekday' THEN Total_Sales END), 0) AS Weekday_Sale,
        COALESCE(SUM(CASE WHEN Weekend_Weekday = 'Weekend' THEN Total_Sales END), 0) AS Weekend_Sale
    FROM sales_summary
    GROUP BY Month_Name
),
-- Calculate Total Sales for each Month
total_sales AS (
    SELECT
        Month_Name,
        SUM(Weekday_Sale + Weekend_Sale) AS Total_Sale
    FROM pivot_sales
    GROUP BY Month_Name
)
-- Final output combining Weekday Sale, Weekend Sale, and Total Sale
SELECT
    ps.Month_Name AS Month_Name,
    ps.Weekday_Sale,
    ps.Weekend_Sale,
    ts.Total_Sale
FROM pivot_sales ps
JOIN total_sales ts
    ON ps.Month_Name = ts.Month_Name
ORDER BY 
    STR_TO_DATE(CONCAT('01 ', ps.Month_Name), '%d %M')  -- Ordering by the chronological month
;
```
#### 📝 **Output:**
| **Month** | **Weekday_Sale** | **Weekend_Sale** | **Total_Sale** |
|-----------|------------------|------------------|----------------|
| **January**   | $58,513.11       | $23,164.63       | $81,677.74     |
| **February**  | $54,002.67       | $22,142.52       | $76,145.19     |
| **March**     | $73,367.33       | $25,467.35       | $98,834.68     |
| **April**     | $79,592.51       | $39,348.57       | $118,941.08    |
| **May**       | $116,627.84      | $40,099.92       | $156,727.76    |
| **June**      | $121,484.08      | $45,001.80       | $166,485.88    |

- **Query 11:** 🛍️ **Sales by Product Category**
```SQL
select product_category, Sum(transaction_qty*unit_price) as Total_Sale
from coffee_shop_sale
where month(transaction_date) = 3
group by product_category
order by Total_Sale desc
limit 5;
```
#### 📝 **Output:**
| **Product Category**    | **Total_Sale** |
|-------------------------|----------------|
| **Coffee**              | $38,303.60     |
| **Tea**                 | $27,910.65     |
| **Bakery**              | $11,902.58     |
| **Drinking Chocolate**  | $10,253.50     |
| **Coffee beans**        | $5,256.20      |

- **Query 12:** 📦 **Sales by Product Type**
```SQL
select product_type, Sum(transaction_qty*unit_price) as Total_Sale
from coffee_shop_sale
where month(transaction_date) = 3
group by product_type
order by Total_Sale desc
limit 5;
```
#### 📝 **Output:**
| **Product Type**          | **Total_Sale** |
|---------------------------|----------------|
| **Barista Espresso**      | $13,078.20     |
| **Brewed Chai tea**       | $11,029.65     |
| **Hot chocolate**         | $10,253.50     |
| **Gourmet brewed coffee** | $9,789.10      |
| **Brewed Black tea**      | $6,875.00      |

## 🔚 **Conclusion**
This project demonstrates a **comprehensive approach** to analyzing coffee shop sales data using **SQL** and **Power BI**. From **data preparation** and **cleaning** to **advanced visualization**, each step contributes to a thorough understanding of **sales trends**, **order patterns**, and **product performance**. The final deliverable is a set of **dynamic and interactive dashboards** that provide actionable insights for **business decision-making**.

## 🛠️ **Tools and Technologies**
- **SQL:** For data extraction and manipulation.
- **Power BI:** For creating dynamic dashboards and visualizations.
- **Google Docs:** For documenting the project.
- **Excel:** For data preparation and initial analysis.

## 🧠 **Skills Demonstrated**
- **Data cleaning and transformation** in SQL.
- **Advanced SQL querying techniques**.
- **Interactive dashboard creation** in Power BI.
- **Documentation and presentation** of project findings.

## 📁 **Project Materials**

- **📄 [Dataset (CSV)](https://github.com/Bhushan148/Coffee-Shop-Sales-Analysis/blob/main/Coffee%20Shop%20Dataset.csv)**
- **📊 [PPT About Project](https://github.com/Bhushan148/Coffee-Shop-Sales-Analysis/blob/main/Coffee%20Shop%20Sales.pptx
)**
- **📝 [SQL Query Document](https://github.com/Bhushan148/Coffee-Shop-Sales-Analysis/blob/main/Coffee%20Shop%20Sales%20SQL%20Query%20Document.pdf)**
- **🌐 [See Live Dashboard Here](https://app.powerbi.com/reportEmbed?reportId=1269a965-11e3-412d-bcec-d4ba9179c81e&autoAuth=true&ctid=b5e77a2d-6845-4cd5-8cc6-828b3b988bb5)**


## 🖼️ **Project Images**

![Page 1](https://github.com/Bhushan148/Coffee-Shop-Sales-Analysis/blob/main/Other%20Project%20Material/Page%201.png)
![Page 2](https://github.com/Bhushan148/Coffee-Shop-Sales-Analysis/blob/main/Other%20Project%20Material/Page%202.png)
![Page 3](https://github.com/Bhushan148/Coffee-Shop-Sales-Analysis/blob/main/Other%20Project%20Material/Page%203.png)
![Page 4](https://github.com/Bhushan148/Coffee-Shop-Sales-Analysis/blob/main/Other%20Project%20Material/Page%204.png)


## 🌐 **Connect with Me**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/bhushan-gawali-97b645233?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app) 
[![Portfolio](https://img.shields.io/badge/Portfolio-000?style=for-the-badge&logo=google-chrome&logoColor=white)](https://bhushan148.github.io/Portfolio-Bhushan-Gawali/) 
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](http://instagram.com/bhushangawali_148)
[![WhatsApp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](http://Wa.me/+917743927365)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Bhushan148) 

