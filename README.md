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
- **Query 2:** 📊 **MoM Growth and Difference for Sales**
- **Query 3:** 📅 **Total Sales Monthly**
- **Query 4:** 🛒 **Total Orders Monthly**
- **Query 5:** 📦 **Total Quantity Monthly**
- **Query 6:** 📈 **MoM Growth and Difference for Orders**
- **Query 7:** 🔄 **MoM Growth and Difference for Quantity Sold**
- **Query 8:** 🏢 **Sales by Store Location for March**
- **Query 9:** 📅 **Calculate Daily Sales Matrix and Include Average Daily Sale**
- **Query 10:** 📆 **Weekend and Weekday Sales**
- **Query 11:** 🛍️ **Sales by Product Category**
- **Query 12:** 📦 **Sales by Product Type**

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

## 🖼️ **Project Images**

![Page 1](https://github.com/Bhushan148/Coffee-Shop-Sales-Analysis/blob/main/Other%20Project%20Material/Page%201.png)
![Page 2](https://github.com/Bhushan148/Coffee-Shop-Sales-Analysis/blob/main/Other%20Project%20Material/Page%202.png)
![Page 3](https://github.com/Bhushan148/Coffee-Shop-Sales-Analysis/blob/main/Other%20Project%20Material/Page%203.png)
![Page 4](https://github.com/Bhushan148/Coffee-Shop-Sales-Analysis/blob/main/Other%20Project%20Material/Page%204.png)


## 🌐 **Connect with Me**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/your-profile) 
[![Portfolio](https://img.shields.io/badge/Portfolio-000?style=for-the-badge&logo=google-chrome&logoColor=white)](https://yourportfolio.com) 
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/your-profile)
[![WhatsApp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://wa.me/your-number)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/your-profile) 

