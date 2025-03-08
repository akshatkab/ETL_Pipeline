# Data Pipeline in Databricks – Schema Inference & Transformation

## Overview
This repository provides a structured approach to handling data in **Databricks**, including ingestion, schema inference, transformations, and referential integrity validation. The project follows best practices for managing fact and dimension tables, ensuring data consistency through normalization and **Snowflake Schema** principles.

## Steps to Validate the Process

### **1. Data Ingestion**
- Upload all raw data files to **Databricks FileStore** or **AWS S3** as the ingestion layer.
- Read the raw data without modifying its structure.
  Refer (ELT_pipeline notebook for more clarification while reading gzip files)
- Save it as a **table** in Databricks.

### **2. Schema Inference & Initial Validation**
- Read the ingested table to analyze its schema.
- Validate column names and data types.
- Identify primary key–foreign key relationships between fact and dimension tables.

### **3. Data Transformation & Quality Checks**
- Load the table from the database.
- Perform **transformations** such as:
  - Filtering unnecessary records.
  - Extracting meaningful attributes.
  - Checking for **unique values** to identify duplicates.
- Apply business rules for cleaning and structuring the dataset.

### **4. Storing Transformed Data**
- Save the cleaned and transformed dataset into a new table for downstream processing.
- Maintain referential integrity and **normalize** data where applicable.

### **5. Entity Relationship Diagram**
- Refer ER Diagram Document file for viewing their relationship.

## Running the Pipeline
1. Upload your dataset to Databricks FileStore or AWS S3.
2. Run the ELT_pipeline notebook's script to load the raw data into tables.
3. Execute the transformation scripts for cleaning and filtering (mentioned in Silver Layer Cell).
4. Store the final processed data to AWS redshift/AWS s3 for business analysis (mentioned in Gold Layer Cell).

## Technologies Used
- **Databricks Community Edition**
- **Apache Spark (PySpark)**
- **AWS S3** (Optional for cloud storage)
- **SQL** for transformations

## Contribution
Feel free to raise an issue or submit a pull request if you have improvements or find any discrepancies.
