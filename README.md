# Data Warehouse & Analytics Project

This project implements a Data Warehouse using SQL Server, focused on data integration, data cleaning, and data modeling for business analytics.

The architecture follows the **Medallion Architecture** approach with three layers: **Bronze**, **Silver**, and **Gold**. Data is loaded from CSV files related to CRM and ERP systems, then transformed into an analytical model ready for SQL queries and reporting.

## Objective

The main goal of this project is to consolidate customer, product, and sales data into a structured Data Warehouse that supports analysis and decision-making.

## Architecture

<img width="1492" height="758" alt="Data_architecture" src="https://github.com/user-attachments/assets/8150f629-49ed-4671-934d-4f4de9724e23" />


### Bronze Layer

The Bronze layer stores raw data from the source systems.

- Loads data from CSV files
- Keeps the original structure of the source data
- No business transformations are applied
- Used for traceability and raw data storage

### Silver Layer

The Silver layer contains cleaned and standardized data.

- Data cleaning
- Data standardization
- Data validation
- Handling missing or incorrect values
- Preparing data for integration

### Gold Layer

The Gold layer contains business-ready data for analytics.

- Dimensional data model
- Fact and dimension tables
- Star schema design
- Data prepared for reporting and SQL analysis

## Technologies Used

- SQL Server
- T-SQL
- SQL Server Management Studio
- Draw.io
- Git & GitHub
- CSV Files

## Repository Structure

```text
data-warehouse-project/
│
├── datasets/      # Raw CSV files
├── docs/          # Documentation and diagrams
├── scripts/       # SQL scripts by layer
│   ├── bronze/
│   ├── silver/
│   └── gold/
├── tests/         # Data quality checks
└── README.md
```

## Naming Conventions

This project uses `snake_case` to keep database object names consistent and easy to read.

Examples:

```text
crm_customer_info
erp_sales_order
dim_customers
fact_sales
```

Main conventions:

| Object | Convention | Example |
|---|---|---|
| Bronze tables | source_entity | crm_customer_info |
| Silver tables | source_entity | crm_customer_info |
| Gold dimensions | dim_entity | dim_customers |
| Gold facts | fact_entity | fact_sales |
| Technical columns | dw_column_name | dw_load_date |

## Skills Practiced

- Data Warehousing
- ETL Development
- SQL Development
- Data Cleaning
- Data Modeling
- Star Schema Design
- Data Quality Checks
- Technical Documentation
- Git Version Control
