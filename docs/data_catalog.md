# Data Catalog - Gold Layer

## Overview

The Gold Layer contains the final business-ready data of the Data Warehouse.

This layer is used for analysis, dashboards, and reports.  
It is mainly organized into:

- Dimension tables
- Fact tables

Dimension tables describe the main business entities, such as customers and products.  
Fact tables store measurable events, such as sales.

---

# 1. gold.dim_customers

## Purpose

This table stores customer information.

It combines customer details with extra demographic and geographic data, such as country, gender, marital status, and birthdate.

## Columns

| Column Name | Data Type | Description |
|---|---|---|
| customer_key | INT | Surrogate key used to identify each customer in the dimension table. |
| customer_id | INT | Original customer ID from the source system. |
| customer_number | NVARCHAR(50) | Customer business number or code. |
| first_name | NVARCHAR(50) | Customer first name. |
| last_name | NVARCHAR(50) | Customer last name. |
| country | NVARCHAR(50) | Customer country. |
| marital_status | NVARCHAR(50) | Customer marital status. |
| gender | NVARCHAR(50) | Customer gender. |
| birthdate | DATE | Customer date of birth. |
| create_date | DATE | Date when the customer record was created. |

---

# 2. gold.dim_products

## Purpose

This table stores product information.

It contains product details such as name, category, subcategory, cost, product line, and start date.

## Columns

| Column Name | Data Type | Description |
|---|---|---|
| product_key | INT | Surrogate key used to identify each product in the dimension table. |
| product_id | INT | Original product ID from the source system. |
| product_number | NVARCHAR(50) | Product business code or number. |
| product_name | NVARCHAR(50) | Product name. |
| category_id | NVARCHAR(50) | ID of the product category. |
| category | NVARCHAR(50) | Main product category. |
| subcategory | NVARCHAR(50) | More specific product category. |
| maintenance_required | NVARCHAR(50) | Shows if the product requires maintenance. |
| cost | INT | Product cost. |
| product_line | NVARCHAR(50) | Product line or series. |
| start_date | DATE | Date when the product became available. |

---

# 3. gold.fact_sales

## Purpose

This table stores the sales transactions.

It connects customers and products using their surrogate keys and contains the main sales measures, such as sales amount, quantity, and price.

## Columns

| Column Name | Data Type | Description |
|---|---|---|
| order_number | NVARCHAR(50) | Sales order number. |
| product_key | INT | Key used to connect the sale with the product dimension. |
| customer_key | INT | Key used to connect the sale with the customer dimension. |
| order_date | DATE | Date when the order was placed. |
| shipping_date | DATE | Date when the order was shipped. |
| due_date | DATE | Date when the order was due. |
| sales_amount | INT | Total sales amount for the order line. |
| quantity | INT | Number of product units sold. |
| price | INT | Price per product unit. |

---

The Gold Layer is the final layer of the Data Warehouse.

In this project:

- `gold.dim_customers` describes the customers.
- `gold.dim_products` describes the products.
- `gold.fact_sales` stores the sales transactions.

The fact table uses `customer_key` and `product_key` to connect with the dimension tables.

This structure makes it easier to create reports and dashboards because the data is already cleaned, organized, and ready for analysis.
