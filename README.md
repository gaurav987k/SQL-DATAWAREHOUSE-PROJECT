# SQL Data Warehouse Project

## Overview
This project demonstrates the design and implementation of a modern Data Warehouse using Microsoft SQL Server. It covers the complete data warehousing pipeline, including data extraction, transformation, loading (ETL), dimensional modeling, and analytical query processing.

The goal of this project is to simulate a real-world business intelligence environment where raw data is transformed into meaningful insights for reporting and decision-making.

---

## Objectives
- Design and implement a Data Warehouse architecture
- Perform ETL (Extract, Transform, Load) using SQL Server
- Implement dimensional data modeling (Star Schema)
- Create fact and dimension tables
- Perform data cleaning and transformation
- Enable analytical querying for business insights
- Demonstrate SQL skills relevant to Data Analyst / Data Engineer roles

---

## Project Architecture

![Data Warehouse Architecture](docs/data_architecture_deh.png)

```
Source Data (CSV Files)
        ↓
Staging Layer (Raw Tables)
        ↓
Data Transformation (ETL Scripts)
        ↓
Data Warehouse Layer
    • Fact Tables
    • Dimension Tables
        ↓
Analytics & Reporting Queries
```

---

## Folder Structure

```
SQL-DATAWAREHOUSE-PROJECT/
│
├── dataset/
│   ├── raw data files
│
├── scripts/
│   ├── create staging tables.sql
│   ├── create warehouse tables.sql
│   ├── ETL scripts.sql
│   ├── transformation scripts.sql
│
├── docs/
│   ├── schema diagrams
│   ├── documentation
│
├── tests/
│   ├── testing queries.sql
│
└── README.md
```

---

## Data Warehouse Design

### Dimension Tables
- dim_customer
- dim_product
- dim_date
- dim_store

These tables store descriptive attributes used for filtering and grouping.

### Fact Tables
- fact_sales

This table stores measurable business metrics such as:
- sales amount
- quantity
- revenue

---

## ETL Process

### Extract
- Import raw data from CSV files into staging tables

### Transform
- Clean data
- Remove duplicates
- Standardize formats
- Apply business logic

### Load
- Load transformed data into dimension tables
- Load transactional data into fact tables

---

## Technologies Used

- Microsoft SQL Server
- T-SQL (Transact-SQL)
- SQL Server Management Studio (SSMS)
- Data Warehousing Concepts
- ETL Process
- Dimensional Modeling

---

## Key Features

- Complete end-to-end Data Warehouse implementation
- ETL pipeline using SQL
- Star schema design
- Analytical query support
- Production-style folder structure

---

## Example Analytical Queries

```sql
-- Total Sales by Product
SELECT 
    p.product_name,
    SUM(f.sales_amount) AS total_sales
FROM fact_sales f
JOIN dim_product p
ON f.product_id = p.product_id
GROUP BY p.product_name;

-- Monthly Sales Trend
SELECT 
    d.month,
    SUM(f.sales_amount) AS monthly_sales
FROM fact_sales f
JOIN dim_date d
ON f.date_id = d.date_id
GROUP BY d.month
ORDER BY d.month;
```

---

## How to Run the Project

1. Install SQL Server and SSMS

2. Clone the repository

```bash
git clone https://github.com/gaurav987k/SQL-DATAWAREHOUSE-PROJECT.git
```

3. Open SQL Server Management Studio

4. Run scripts in order:

```
1. Create staging tables
2. Load dataset
3. Run transformation scripts
4. Create warehouse tables
5. Load fact and dimension tables
```

---

## Skills Demonstrated

- SQL Development
- Data Warehousing
- ETL Development
- Data Modeling
- Database Design
- Analytical Query Writing

---

## Author

**Gaurav Kanojiya**  
Electronics & Telecommunication Engineering Student  
Aspiring Data Analyst / Data Engineer  

GitHub: https://github.com/gaurav987k

---

## License

This project is licensed under the MIT License.
