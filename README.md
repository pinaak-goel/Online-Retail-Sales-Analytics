# Online Retail Sales Analytics Project

This project demonstrates a full end-to-end ETL pipeline using Apache Airflow, BigQuery, and dbt, processing an online retail dataset. The workflow covers data extraction, transformation, quality checks, and reporting through tasks integrated into Airflow.

## Dataset
The dataset used in this project is the [Online Retail Dataset](https://www.kaggle.com/datasets/tunguz/online-retail), which contains transactional data for an e-commerce business.

### Dataset Columns
- `InvoiceNo`: Unique 6-digit invoice number for each transaction.
- `StockCode`: Product (item) code.
- `Description`: Product name.
- `Quantity`: Number of items per transaction.
- `InvoiceDate`: Date and time of the transaction.
- `UnitPrice`: Price per product.
- `CustomerID`: Unique 5-digit customer ID.
- `Country`: Name of the country where the customer resides.

## Project Overview
This pipeline extracts data from a CSV file, uploads it to Google Cloud Storage (GCS), and then processes it in BigQuery for analysis and reporting using dbt models.

### Tools & Technologies
- **Apache Airflow**: Workflow orchestration.
- **Google Cloud Storage (GCS)**: Data storage.
- **BigQuery**: Data warehouse for processing and analytics.
- **dbt (Data Build Tool)**: Transformation layer.
- **Soda**: Data quality checks.
- **Metabase**: Visualization and reporting.

## Prerequisites
- Docker
- Astro CLI
- Google Cloud account with permissions for GCS and BigQuery

## Pipeline Steps

### 1. Setup Environment
- **Airflow Docker Environment**: Ensure you're using `quay.io/astronomer/astro-runtime:8.8.0` or `airflow 2.6.1` in your Dockerfile. Use Astro CLI to manage and restart Airflow if necessary.
  
### 2. Data Ingestion
- **Dataset**: Download the dataset from [Kaggle](https://www.kaggle.com/datasets/tunguz/online-retail).
- **GCS Upload**: Upload the dataset to your GCS bucket using Airflow tasks.
  
### 3. BigQuery Setup
- **Create Tables**: Load the raw data into a `raw_invoices` table in BigQuery.
  
### 4. Data Transformation (dbt)
- Create dimension tables like `dim_customer`, `dim_datetime`, and `dim_product`.
- Build a fact table `fct_invoices` by joining dimension tables and calculating metrics.

### 5. Data Quality Checks (Soda)
- **Schema Validation**: Ensure correct data types and missing columns are handled.
- **Null Checks**: Ensure no null values in key columns.
- **Duplicate Checks**: Check for duplicate entries in key fields like `invoice_id`, `product_id`, etc.
  
### 6. Reporting
- **Metabase Dashboard**: Visualize total revenue, invoices, and top products using predefined SQL queries in dbt.
