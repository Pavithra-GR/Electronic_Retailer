# 📊 Electronics Retailer KPI Analysis using Databricks

## 📌 Project Overview

This project is an end-to-end retail data analytics pipeline built using **Azure**, **Databricks**, and **SQL**.  

The objective of this project is to process raw retail datasets and generate meaningful business insights for an electronics retailer company.

The company operates across multiple countries and sales channels (Online and In-Store) and wants to analyze:
- Revenue growth
- Product performance
- Customer behavior
- Delivery efficiency
- Channel performance
- Customer loyalty

The project follows the **Medallion Architecture** approach:
- Bronze Layer → Raw Data
- Silver Layer → Cleaned Data
- Gold Layer → Analytics & KPIs


# 🏗 Architecture Used

## Medallion Architecture

### 🥉 Bronze Layer
Stores raw data exactly as received from source files.

### 🥈 Silver Layer
Performs:
- Data cleaning
- Null handling
- Data type conversion
- Standardization
- Data transformation

### 🥇 Gold Layer
Contains:
- Fact tables
- Dimension tables
- Data cube
- KPI-ready analytical tables


# ☁️ Technologies Used

| Component | Technology |
|---|---|
| Cloud Storage | Azure Storage Account |
| Data Processing | Databricks |
| Query Language | SQL |
| Data Source | Excel Files |
| Data Modeling | Star Schema |
| Architecture | Medallion Architecture |


# 📂 Dataset Information

The project uses the following datasets:

## 1. Sales
Contains transactional order details

## 2. Customers
Contains customer-related information

## 3. Products
Contains product details:


## 4. Stores
Contains store-related information:

## 5. Exchange Rates
Contains currency conversion rates.

Used to convert all revenue values into USD.


# 🔄 Project Workflow

## Step 1: Azure Storage Setup

- Created Azure Storage Account
- Created container
- Uploaded all raw Excel datasets


## Step 2: Databricks Setup

- Connected Azure Storage with Databricks using fivetran
- Created Catalog
- Created Schemas:
  - Bronze
  - Silver
  - Gold


## Step 3: Bronze Layer

Imported raw datasets from Azure Storage into Bronze tables.

Purpose:
- Store original data
- Maintain traceability
- Backup raw source

No transformations applied here.

## Step 4: Silver Layer

Performed data cleaning and transformation:
- Renamed columns
- Converted datatypes
- Removed null values
- Standardized column formats
- Cleaned inconsistent records

# Step 5: Gold Layer

In the Gold layer, the cleaned and transformed data from the Silver layer is modeled for analytics and reporting purposes.

The Gold layer contains:
- Fact tables
- Dimension tables
- Data cube

This layer is optimized for:
- KPI computation
- Reporting
- Business analysis
- Dashboard integration


# 🧊 Data Cube

A centralized analytical data cube was created for KPI computation and multidimensional analysis.

The cube combines:
- Sales
- Customers
- Products
- Stores
- Date dimensions

This data cube enables faster querying and simplifies KPI generation.

# Step 6: Build KPIs

After creating the Gold layer and data cube, Key Performance Indicators (KPIs) were developed to analyze business performance and generate actionable insights.

The KPIs were created using SQL queries on top of the Gold layer tables and data cube.


#  Step 7: Build Pipeline

An end-to-end data pipeline was implemented using Azure Storage and Databricks.

The pipeline automates the flow of data through the Medallion Architecture layers.


## Pipeline Workflow

### 1. Data Ingestion
- Raw Excel files uploaded to Azure Storage
- Data imported into Bronze layer



### 2. Bronze Layer Processing
- Stores raw data without modifications
- Maintains data traceability



### 3. Silver Layer Processing
Data cleaning and transformation:
- Handle null values
- Convert datatypes
- Rename columns
- Standardize formats



### 4. Gold Layer Processing
- Create fact tables
- Create dimension tables
- Build data cube
- Generate analytical datasets


## Pipeline Benefits

The pipeline provides:
- Scalability
- Automation
- Reliable data flow
- Faster analytics
- Reusable architecture

#  Step 8: Build Dashboard

A business dashboard was created using the KPI outputs generated from the Gold layer.

The dashboard provides a visual representation of business performance and supports data-driven decision-making.
