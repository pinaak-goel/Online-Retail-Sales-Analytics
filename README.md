# Retail Data Pipeline with Airflow, DBT, and Cosmos

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Setup](#setup)
  - [Clone the Repository](#clone-the-repository)
  - [Set Up the Environment](#set-up-the-environment)
  - [Configure Google Cloud Storage](#configure-google-cloud-storage)
  - [Install Required Python Packages](#install-required-python-packages)
  - [Initialize Airflow](#initialize-airflow)
  - [Set Up DBT Project](#set-up-dbt-project)
  - [Create BigQuery Tables](#create-bigquery-tables)
  - [Running the Pipeline](#running-the-pipeline)
- [Data Pipeline Overview](#data-pipeline-overview)
  - [Step 1: Upload File to GCS](#step-1-upload-file-to-gcs)
  - [Step 2: Data Quality Checks on Raw Data](#step-2-data-quality-checks-on-raw-data)
  - [Step 3: Transform Data with DBT](#step-3-transform-data-with-dbt)
  - [Step 4: Data Quality Checks on Transformed Data](#step-4-data-quality-checks-on-transformed-data)
- [DBT Models](#dbt-models)
  - [dim_customer](#dim_customer)
  - [dim_datetime](#dim_datetime)
  - [dim_product](#dim_product)
  - [fact_invoices](#fact_invoices)
- [Cosmos Integration](#cosmos-integration)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Overview

This project sets up a retail data pipeline using Apache Airflow, DBT (Data Build Tool), and Cosmos. The pipeline automates the process of ingesting raw data, performing data quality checks, transforming the data into dimension and fact tables, and validating the transformations.

## Prerequisites

Before you begin, ensure you have the following installed:

- [Python 3.8+](https://www.python.org/downloads/)
- [Docker](https://www.docker.com/get-started)
- [GCP]
- [Apache Airflow](https://airflow.apache.org/docs/apache-airflow/stable/start.html)
- [DBT CLI](https://docs.getdbt.com/docs/installation)
- [Cosmos](https://astronomer.github.io/astro-sdk/)
