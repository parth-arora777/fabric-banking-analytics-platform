# 💳 FinSight Banking Analytics Platform

> End-to-End Banking Analytics Platform built on **Microsoft Fabric** using **Medallion Architecture**, **PySpark**, **Delta Lake**, **Dataflow Gen2**, **SQL Analytics Endpoint**, and **Power BI**.

![Microsoft Fabric](https://img.shields.io/badge/Microsoft-Fabric-blue)
![Power BI](https://img.shields.io/badge/Power-BI-yellow)
![PySpark](https://img.shields.io/badge/PySpark-orange)
![Delta Lake](https://img.shields.io/badge/Delta-Lake-green)
![SQL](https://img.shields.io/badge/SQL-Analytics-red)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 📖 Project Overview

Modern banks generate millions of transactions every day alongside customer, branch, and product data. Raw CSV exports are difficult to analyze directly due to inconsistent schemas, poor data quality, and lack of governance.

**FinSight** is an enterprise-style analytics platform built using **Microsoft Fabric** that transforms raw banking datasets into curated business-ready data using the **Medallion Architecture (Bronze → Silver → Gold)**.

The solution demonstrates a complete analytics lifecycle including:

- Data Ingestion
- Data Validation
- Data Cleaning
- Data Transformation
- Business Aggregation
- SQL Serving Layer
- Executive Reporting

---

# 🚀 Business Problem

Retail banks continuously generate transactional and operational data from multiple systems.

Without a structured analytics platform:

- Analysts repeatedly clean the same datasets.
- Fraud monitoring becomes inconsistent.
- Reports use different business logic.
- Raw CSV files cannot efficiently support enterprise reporting.
- Data quality issues propagate into executive dashboards.

The objective of this project was to design a scalable analytics platform capable of converting raw banking datasets into trusted analytical assets.

---

# 🎯 Objectives

✔ Build an end-to-end analytics solution using Microsoft Fabric

✔ Implement Medallion Architecture

✔ Validate incoming data before transformation

✔ Standardize transaction datasets

✔ Build business-ready Gold tables

✔ Create reusable SQL Views

✔ Design interactive Power BI dashboards

✔ Demonstrate enterprise data engineering concepts

---

# 📊 Dataset

| Dataset | Records |
|----------|---------:|
| Transactions | **6,362,620** |
| Customers | **50,000** |
| Branches | **200** |
| Products | **10** |

---

# 🏗 Architecture

```
                  Raw CSV Files
                         │
                         ▼
                Microsoft Fabric Pipeline
                         │
                         ▼
                 Bronze Layer (Delta)
                         │
          Validation & Data Quality Checks
                         │
                         ▼
                 Silver Layer (Delta)
       Cleaning • Enrichment • Standardization
                         │
                         ▼
                  Gold Layer (Delta)
          Business Aggregations & KPIs
                         │
                         ▼
               SQL Analytics Endpoint
                         │
                         ▼
                    Power BI Reports
```

---

# 🛠 Technology Stack

| Category | Technologies |
|------------|--------------|
| Cloud Platform | Microsoft Fabric |
| Storage | OneLake |
| Data Warehouse | Lakehouse |
| Data Format | Delta Lake |
| Compute | Apache Spark (PySpark) |
| Transformation | Dataflow Gen2 |
| Orchestration | Fabric Data Pipeline |
| Serving | SQL Analytics Endpoint |
| Visualization | Power BI |
| Language | SQL, Python |

---

# 📂 Medallion Architecture

## Bronze Layer

Purpose:

- Raw Data Storage
- Initial Validation
- Preserve Original Data

### Validation Performed

- Minimum Row Count
- Null Key Validation
- Duplicate Detection
- Validation Logs

Output:

- bronze_transactions
- bronze_customers
- bronze_products
- bronze_branches

---

## Silver Layer

Purpose:

Transform raw data into clean analytical datasets.

Transformations include:

- Column Renaming
- Data Type Conversion
- Balance Calculations
- Fraud Flags
- Calendar Fields
- Transaction Timestamp
- Data Quality Flags
- Invalid Record Detection

Reference datasets are cleaned using **Dataflow Gen2**.

Output:

- silver_transactions
- silver_customers
- silver_products
- silver_branches

---

## Gold Layer

Business-ready aggregated tables.

Created Gold Tables:

- gold_transaction_summary
- gold_customer_summary
- gold_branch_summary
- gold_product_summary

These tables power the Power BI dashboards.

---

# 🔄 Pipeline Flow

```
Copy Data
      │
      ▼
Bronze Validation Notebook
      │
      ▼
Silver Notebook
      │
      ├────────────► Dataflow Gen2
      │
      ▼
Gold Notebook
      │
      ▼
SQL Views
      │
      ▼
Semantic Model Refresh
      │
      ▼
Power BI Dashboard
```

---

# 📈 Power BI Dashboards

### Executive Dashboard

KPIs

- Total Transactions
- Total Amount
- Average Transaction Amount
- Fraud Count

Visuals

- Transaction Type Distribution
- Fraud Analysis
- Monthly Trends

---

### Customer Analytics

KPIs

- Total Customers
- Active Customers
- Inactive Customers
- Average Income

Visuals

- Customer Segments
- Income Distribution
- Credit Score Analysis
- Age Band Analysis

---

### Product & Branch Analytics

KPIs

- Total Branches
- Average Interest Rate
- Average Fees
- Staff Count

Visuals

- Product Categories
- Branch Distribution
- Fee Analysis
- Active vs Inactive Branches

---

# ⚙ SQL Analytics Endpoint

Business Views Created

- vw_gold_transaction_summary
- vw_gold_customer_summary
- vw_gold_branch_summary
- vw_gold_product_summary
- vw_dashboard

These views provide a stable semantic layer for reporting.

---

# 📋 Data Quality Framework

The project implements an automated validation framework before any transformation begins.

Validation includes:

✔ Row Count Validation

✔ Null Key Detection

✔ Duplicate Detection

✔ Audit Logging

✔ Data Quality Flags

---

# 📊 Business Insights

The platform enables stakeholders to answer questions such as:

- Which transaction types contribute most to fraud?
- Which customer segments are most valuable?
- Which regions require additional staffing?
- Which products generate the highest fees?
- How transaction volume changes over time.

---

# 📁 Repository Structure

```
fabric-banking-analytics-platform/

│
├── README.md
├── docs/
│     Technical_Report.pdf
│
├── notebooks/
│     bronze_validation.ipynb
│     silver_transformation.ipynb
│     gold_aggregation.ipynb
│
├── pipeline/
│     data_pipeline.png
│
├── architecture/
│     architecture.png
│
├── dataflow/
│     customer_dataflow.png
│
├── sql/
│     gold_views.sql
│
├── powerbi/
│     FinSight.pbix
│
├── images/
│     dashboards/
│
└── screenshots/
```

---

# 🎓 Key Learnings

Through this project I gained hands-on experience with:

- Microsoft Fabric
- Medallion Architecture
- Delta Lake
- Data Engineering Concepts
- PySpark
- Data Validation Frameworks
- Power BI
- SQL Analytics Endpoint
- Dataflow Gen2
- Enterprise Reporting

---

# 🚀 Future Improvements

- Incremental Data Loading
- Real-Time Streaming
- CI/CD Deployment Pipelines
- Role Level Security
- Dynamic Data Masking
- Azure Key Vault Integration
- Automated Monitoring
- Fabric Deployment Pipelines

---

# 📌 Skills Demonstrated

- Data Engineering
- Business Intelligence
- Data Analytics
- Data Validation
- Data Modeling
- ETL Pipeline Development
- SQL Development
- Power BI Dashboard Development
- Lakehouse Architecture
- Data Governance

---

# 📷 Screenshots

> Add screenshots here:

- Architecture
- Workspace
- Pipeline
- Bronze Notebook
- Silver Notebook
- Gold Notebook
- Dataflow
- SQL Endpoint
- Dashboard Page 1
- Dashboard Page 2
- Dashboard Page 3

---

# 👨‍💻 Author

**Parth Arora**

Data Analyst | Microsoft Fabric | Power BI | SQL | Python

📧 Email: work.aroraparth@gmail.com

💼 LinkedIn: https://linkedin.com/in/parth-arora-a9a453249

🌐 Portfolio: https://partharoraisop.wixstudio.io/partharora

⭐ If you found this project interesting, consider giving it a star.
