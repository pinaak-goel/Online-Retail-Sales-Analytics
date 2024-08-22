# Retail Data Pipeline with Airflow, DBT, and Cosmos

## Table of Contents

- Overview
- Prerequisites
- Setup
  - Set Up the Environment
  - Configure Google Cloud Storage
  - Install Required Python Packages
  - Initialize Airflow
  - Set Up DBT Project
  - Create BigQuery Tables
  - Running the Pipeline
- Data Pipeline Overview
  - Step 1: Upload CSV to GCS
  - Step 2: Data Quality Checks on Raw Data
  - Step 3: Transform Data with DBT
  - Step 4: Data Quality Checks on Transformed Data
- DBT Models
  - dim_customer
  - dim_datetime
  - dim_product
  - fact_invoices
- Cosmos Integration
- Troubleshooting
- Contributing
- License

## Overview

This project sets up a retail data pipeline using Apache Airflow, DBT (Data Build Tool), and Cosmos. The pipeline automates the process of ingesting raw data, performing data quality checks, transforming the data into dimension and fact tables, and validating the transformations.

## Prerequisites

Before you begin, ensure you have the following installed:

- Python 3.8+
- Docker
- Google Cloud Platform
- Apache Airflow
- DBT CLI
- Cosmos
