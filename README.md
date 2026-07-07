# Azure Databricks Real-World Healthcare End-to-End Project

## Overview
This project demonstrates a production-grade, end-to-end 
Healthcare Data Engineering pipeline built on Azure Databricks, 
following industry best practices and real-world project standards.

## Architecture
Medallion Architecture (Bronze → Silver → Gold)

Landing Zone → Bronze → Silver → Gold
     │              │         │        │
  Raw Files     Ingested   Cleaned  Aggregated
  (ADLS)        Delta      Delta     Delta
                Tables     Tables    Tables

## Tech Stack
- Azure Databricks
- Delta Lake & Delta Live Tables (DLT)
- Unity Catalog
- Azure Data Lake Storage (ADLS Gen2)
- PySpark & Spark Structured Streaming
- Databricks Asset Bundles (DABs) — CI/CD
- GitHub Actions — Deployment Pipeline
- Azure Active Directory — Service Principal Auth

## Project Highlights
- Medallion Architecture with Bronze, Silver, Gold layers
- Incremental data loading using trigger(availableNow=True)
- Data quality checks using DLT Expectations
- CI/CD pipeline using Databricks Asset Bundles (DABs)
- Unity Catalog for centralized governance & access control
- Service Principal based secure authentication
- Parameterized notebooks using dbutils.widgets
- Structured Streaming with checkpointing

## Project Structure
├── notebooks/
│   ├── bronze/          # Raw ingestion notebooks
│   ├── silver/          # Transformation notebooks
│   └── gold/            # Aggregation notebooks
├── resources/           # Cluster & job configs
├── databricks.yml       # DABs configuration
└── README.md

## Pipeline Flow
1. Raw healthcare data lands in ADLS (Landing Zone)
2. Bronze Layer  — Ingests raw data as-is using Auto Loader
3. Silver Layer  — Cleans, validates, and transforms data
4. Gold Layer    — Aggregates for reporting and analytics
5. CI/CD         — DABs deploys across Dev → Staging → Prod

## Author
**Ashish Tripathi**
- GitHub: github.com/ashishtripathi2110
- Email: ashishtripathi2110@gmail.com
