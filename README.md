# 📊 Sales Data Warehouse & Power BI Dashboard

> **Description:**  
> End-to-end data analytics solution built with **SQL Server**, **SSIS**, and **Power BI** to transform raw sales data into actionable business insights.  
> The project features a **Star Schema Data Warehouse**, **dynamic ETL pipelines** (initial and incremental loads), **Slowly Changing Dimensions (SCDs)** for historical tracking, and **Columnstore Indexes** for fast analytics.  
> The data warehouse powers a fully interactive **Power BI dashboard** that visualizes sales trends, profit performance, and product-level KPIs for data-driven decision-making.

---

## 🔧 Key Features

### 🧩 Star Schema Design
- Fact table: `FactSales`  
- Dimension tables: `DimCustomer`, `DimProduct`, `DimDate`, `DimGeography`  
- Optimized for fast OLAP queries and interactive reporting.

### ⚙️ ETL Process (SSIS)
- Automated **initial** and **incremental loads** from OLTP to DW.  
- Includes **staging tables**, data validation, error handling, and logging.  
- Uses a **Watermark Table** to track incremental updates.

### 🕒 Slowly Changing Dimensions (SCDs)
- Type 2 SCDs for Product dimension (tracking price and category changes).  
- Maintains full historical accuracy for analysis over time.

### ⚡ Columnstore Indexes
- Applied **Clustered Columnstore Indexes** on `FactSales` for high-performance analytics.

### 📈 Power BI Dashboard
- Interactive visuals:  
  - Sales trends over time  
  - Profit performance by region and product category  
  - Product-level KPIs (Sales, Profit, Margin %, Quantity)  
  - Dynamic filtering and comparative analysis

---

## ⚙️ Tools & Technologies

| Category | Tools Used |
|-----------|-------------|
| Database & ETL | SQL Server, SSIS (SQL Server Integration Services) |
| Data Modeling | Star Schema, OLAP Design, SCDs |
| Query Language | T-SQL |
| Visualization | Power BI |
| Optimization | Columnstore Indexes, Incremental Loading |
| Version Control | Git & GitHub |

---

## 🔄 ETL Flow Overview

```mermaid
graph TD
    A[OLTP Database] --> B[SSIS ETL Packages]
    B --> C[Staging Database]
    C --> D[Data Warehouse (DW)]
    D --> E[Power BI Dashboard]
