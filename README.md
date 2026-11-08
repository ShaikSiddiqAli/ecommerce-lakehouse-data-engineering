# ecommerce-lakehouse-data-engineering
# E-Commerce Lakehouse Data Engineering Project

## 1. Project Overview

**Project Name:** E-Commerce Lakehouse Data Engineering Pipeline

**Platform:** Databricks Community Edition

**Domain:** E-Commerce / Retail Analytics

**Objective:** Build a data engineering pipeline that ingests raw e-commerce transaction data, stores it in a Bronze layer, transforms it into a Silver layer, and generates useful business analytics.

## 2. Problem Statement

E-commerce businesses generate large volumes of transactional data. Raw datasets may contain missing customer information, cancelled orders, negative quantities, invalid prices, and duplicate records.

The objective of this project is to build a structured data pipeline that organizes, processes, and validates retail transaction data to support reliable analytics.

## 3. Technology Stack

- Databricks Community Edition
- Python
- PySpark
- SQL
- Delta Lake / Delta Tables
- Databricks Jobs
- E-Commerce Online Retail Dataset

## 4. Project Architecture

The project follows a Medallion Architecture.

**Bronze Layer → Silver Layer → Analytics**

### Bronze Layer
- Ingested raw online retail transaction data.
- Created the `bronze_online_retail` table.
- Preserved the source data for downstream processing.

### Silver Layer
- Applied data cleaning and transformation.
- Created the `silver_online_retail` table.
- Examined missing CustomerID values.
- Investigated negative quantities and zero or negative prices.
- Prepared structured data for analytical queries.

### Analytics Layer
- Calculated invoice counts.
- Calculated unique customer counts.
- Calculated net quantities.
- Calculated net sales.

## 5. ETL Workflow

1. Downloaded the e-commerce dataset.
2. Created a Databricks notebook.
3. Loaded the raw dataset.
4. Performed initial data exploration.
5. Identified missing and invalid values.
6. Created the Bronze table.
7. Applied cleaning and transformation operations.
8. Created the Silver table.
9. Performed data quality checks.
10. Created a Databricks Job.
11. Executed the pipeline.
12. Verified analytical outputs.

## 6. Data Quality Observations

The Silver table was examined for the following conditions:

| Data quality check | Observed records |
|---|---:|
| Missing CustomerID | 135,037 |
| Negative Quantity | 10,587 |
| Zero Quantity | 0 |
| Zero UnitPrice | 2,512 |

These records require appropriate business treatment. Negative quantities can represent returns or cancellations, while missing customer identifiers limit customer-level analysis.

## 7. Final Analytical Results

The following results were obtained from the Silver table:

| Metric | Result |
|---|---:|
| Total invoices | 25,900 |
| Unique customers | 4,372 |
| Net quantity | 5,162,502 |
| Net sales | 9,726,006.95 |

*Net sales are calculated using Quantity × UnitPrice, including negative-quantity transactions.*

## 8. Pipeline Execution

A Databricks Job named `run_ecommerce_pipeline` was created.

Execution results:
- Job creation: Successful
- Notebook task: Configured
- Compute: Serverless
- First execution: Succeeded
- Second execution: Succeeded

This demonstrates that the notebook can be executed through the Databricks Jobs interface.

## 9. Project Outcomes

- Implemented a Bronze-to-Silver data processing workflow.
- Created structured tables for retail transaction data.
- Practiced PySpark and SQL transformations.
- Examined data quality issues.
- Generated business-level sales metrics.
- Configured and executed a Databricks Job.

## 10. Future Improvements

- Implement a Gold layer for business-ready analytics.
- Improve handling of missing customer information.
- Separate returns and cancellations from normal sales.
- Add automated data quality assertions.
- Add incremental data ingestion.
- Build a Power BI or Tableau dashboard.

## 11. Conclusion

This project demonstrates the implementation of a foundational E-Commerce Lakehouse Data Engineering Pipeline using Databricks.

It provides practical experience with data ingestion, transformation, structured storage, data quality investigation, SQL analytics, and job orchestration.

The project establishes a foundation for developing more advanced and scalable data engineering solutions.
