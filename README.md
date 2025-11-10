# 📊 Sales Data Warehouse & Power BI Dashboard

> **Description:**  
> A complete end-to-end data analytics solution built with **SQL Server**, **SSIS**, and **Power BI** to transform raw transactional data into actionable business insights.  
> The project involves designing and implementing a **Star Schema Data Warehouse**, developing **dynamic ETL pipelines** (initial and incremental loads), handling **Slowly Changing Dimensions (SCDs)** for historical tracking, and optimizing analytical queries with **Columnstore Indexes**.  
> The data warehouse powers a fully interactive **Power BI dashboard** that visualizes sales performance, profit trends, and product-level insights — empowering data-driven decision-making across business units.

---

## 🔧 Key Features

### 🧩 Star Schema Design
- Designed a **Star Schema** consisting of **FactSales** (fact table) and multiple **Dim tables** such as Customer, Product, and Date.  
- Enables simplified querying and fast aggregations in Power BI and SQL Server Analysis.

### ⚙️ ETL Process (SSIS)
- Built **SSIS packages** to automate **Initial Loads** and **Incremental Loads** from the operational database (OLTP).  
- Implemented a **Watermark Table** to track last extraction dates for incremental runs.  
- Integrated error handling, data validation, and logging mechanisms for reliability.

### 🕒 Slowly Changing Dimensions (SCDs)
- Implemented **Type 2 SCDs** for the Product dimension to maintain historical cost and price changes.  
- Used **SSIS SCD transformations** and custom T-SQL logic for efficient updates.

### ⚡ Columnstore Indexes
- Applied **Clustered Columnstore Indexes** on the `FactSales` table to significantly improve query performance for analytical workloads.

### 🗄️ Data Warehouse in SQL Server
- Developed the entire Data Warehouse in **SQL Server** under the `[AdventureWorks-DW].[Sales]` schema.  
- Ensured referential integrity and optimized table relationships for OLAP analysis.

### 📈 Power BI Dashboard
- Built a visually rich **Power BI dashboard** on top of the OLAP model to analyze:
  - 🕑 Sales trends over time (yearly, monthly, daily)
  - 🌍 Profit performance by region, product category, and customer segment
  - 📊 Product-level KPIs (Sales, Profit, Margin %, Quantity)
  - 📉 Comparative analysis and dynamic filtering (date, region, product)

---

## ⚙️ Tools & Technologies

| Category | Tools Used |
|-----------|-------------|
| **Database & ETL** | SQL Server, SSIS (SQL Server Integration Services) |
| **Data Modeling** | Star Schema, OLAP Design, SCDs |
| **Query Language** | T-SQL |
| **Visualization** | Power BI |
| **Optimization** | Columnstore Indexes, Incremental Loading |
| **Version Control** | Git & GitHub |

---

## 🔄 ETL Flow Overview

```mermaid
graph TD
A[OLTP Database] --> B[SSIS ETL Packages]
B --> C[Staging Database]
C --> D[Data Warehouse (DW)]
D --> E[Power BI Dashboard]
