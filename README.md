# 🏗️ SQL Data Warehouse Project

> An end-to-end SQL Data Warehouse built with SQL Server. This project transforms raw CRM and ERP data into a clean, analytics-ready model through a layered ETL pipeline, data-quality checks, and a star-schema design.

[![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)](https://www.microsoft.com/sql-server)
[![T-SQL](https://img.shields.io/badge/T--SQL-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)](https://learn.microsoft.com/sql/t-sql/)
[![Architecture](https://img.shields.io/badge/Architecture-Medallion-5B5FC7?style=for-the-badge)](#-data-architecture)
[![ETL](https://img.shields.io/badge/ETL-Batch_Processing-0E7490?style=for-the-badge)](#-etl-pipeline)
[![License](https://img.shields.io/badge/License-MIT-16A34A?style=for-the-badge)](LICENSE)

---

## 📸 Project Preview

![Data Warehouse Architecture](docs/Data%20Architecture.png)

---

## 📑 Table of Contents

- [Project Overview](#-project-overview)
- [Data Architecture](#-data-architecture)
- [Data Flow](#-data-flow)
- [Data Integration](#-data-integration)
- [Tech Stack](#-tech-stack)
- [ETL Pipeline](#-etl-pipeline)
- [Data Model](#-data-model)
- [Repository Structure](#-repository-structure)
- [How to Run](#-how-to-run)
- [Data Quality Testing](#-data-quality-testing)
- [Future Improvements](#-future-improvements)
- [Credits](#-credits)
- [Author](#-author)

---

## 🎯 Project Overview

This project demonstrates how to build a modern SQL Data Warehouse from scratch. It ingests source data from CRM and ERP systems, standardizes and enriches it through ETL processes, and delivers an analytical data model designed for reporting and business insights.

| Item | Description |
|---|---|
| **Project Type** | SQL Data Warehouse |
| **Database** | Microsoft SQL Server |
| **Architecture** | Medallion Architecture: Bronze, Silver, and Gold |
| **Source Systems** | CRM and ERP CSV extracts |
| **Processing** | Batch ETL with T-SQL stored procedures |
| **Data Modeling** | Star Schema |
| **Data Quality** | Validation and testing scripts |

### Business Objectives

- Consolidate data from multiple operational source systems.
- Build a reliable, repeatable ETL process.
- Create a single source of truth for analytical reporting.
- Model customer, product, and sales data for fast and intuitive analysis.
- Apply data-quality checks before publishing reporting-ready data.

---

## 🏛️ Data Architecture

The solution follows a **Medallion Architecture**. Each layer has a clear responsibility, allowing raw source data to be preserved while progressively improving data quality and business usability.

![Data Architecture](docs/Data%20Architecture.png)

| Layer | Purpose |
|---|---|
| **Bronze** | Stores raw data exactly as received from source systems. |
| **Silver** | Cleans, standardizes, deduplicates, and integrates the raw data. |
| **Gold** | Provides business-ready fact and dimension tables for analytics. |

---

## 🔄 Data Flow

The pipeline extracts source files, loads them into the Bronze layer, applies transformations in Silver, and finally produces curated analytical tables in Gold.

![Data Flow Diagram](docs/Data%20Flow%20Diagram.png)

---

## 🔗 Data Integration

CRM data contributes customer and sales information, while ERP data supplies product and reference information. The integration process aligns shared business entities into one consistent analytical model.

![Data Integration](docs/Data%20Integration.png)

---

## 🧰 Tech Stack

| Tool / Technology | Purpose |
|---|---|
| **SQL Server** | Data warehouse platform and database engine. |
| **T-SQL** | Data ingestion, transformations, and validation logic. |
| **CSV Files** | Source extracts from CRM and ERP systems. |
| **Draw.io** | Architecture and data-model documentation. |
| **Git & GitHub** | Version control and project collaboration. |

---

## ⚙️ ETL Pipeline

### 1. Bronze Layer — Raw Ingestion

- Creates source-aligned tables.
- Loads raw CRM and ERP extracts without business transformations.
- Preserves the original data for traceability and reprocessing.

### 2. Silver Layer — Cleansing & Standardization

- Removes duplicates and handles missing values.
- Standardizes dates, text fields, codes, and naming conventions.
- Applies data-type corrections and business-rule transformations.
- Integrates related CRM and ERP entities.

### 3. Gold Layer — Analytics Delivery

- Builds reporting-ready dimensions and facts.
- Implements the star schema.
- Publishes clean, trusted datasets for BI tools and analysis.

---

## ⭐ Data Model

The Gold layer uses a **star schema** to make reporting simple and performant. The central fact table captures sales activity and connects to descriptive dimensions such as customers, products, and dates.

![Star Schema](docs/Star%20Schema.png)

| Table Type | Examples | Purpose |
|---|---|---|
| **Fact Tables** | `fact_sales` | Stores measurable business events, such as sales amount and quantity. |
| **Dimension Tables** | `dim_customers`, `dim_products`, `dim_dates` | Adds business context for filtering, grouping, and reporting. |

---

## 📁 Repository Structure

```text
sql-data-warehouse-project/
│
├── datasets/                 # Source CRM and ERP files
│   ├── source_crm/
│   └── source_erp/
│
├── docs/                     # Architecture and data-model diagrams
│   ├── data_architecture.png
│   ├── data_flow_diagram.png
│   ├── data_integration.png
│   └── star_schema.png
│
├── scripts/
│   ├── bronze/               # Raw ingestion scripts
│   ├── silver/               # Cleansing and transformation scripts
│   ├── gold/                 # Star-schema and reporting-layer scripts
│   └── tests/                # Data-quality validation scripts
│
├── LICENSE
└── README.md
```

---

## 🚀 How to Run

### Prerequisites

- SQL Server (Developer, Express, or compatible edition)
- SQL Server Management Studio (SSMS), Azure Data Studio, or another SQL client
- Access to the source CSV files in the `datasets/` directory

### Setup

1. Clone this repository.

   ```bash
   git clone https://github.com/Muhamed-Gad/sql_data_warehouse_projecct.git
   ```

2. Open the project in your SQL client and create the database.

3. Run the scripts in this order:

   ```text
   1. scripts/bronze/
   2. scripts/silver/
   3. scripts/gold/
   4. scripts/tests/
   ```

4. Update source file paths in the ingestion scripts if your local folder differs.

5. Query the Gold-layer tables to begin analysis.

---

## ✅ Data Quality Testing

Validation scripts help ensure the data published to the Gold layer is reliable. Typical checks include:

- Null or missing values in required fields.
- Duplicate business keys.
- Invalid dates, quantities, and monetary amounts.
- Orphaned foreign keys between facts and dimensions.
- Reconciliation of record counts across pipeline layers.
- Consistency of standardized values and business rules.

Run the scripts in `scripts/tests/` after each pipeline load and investigate any exceptions before using the data for reporting.

---

## 🔮 Future Improvements

- [ ] Add incremental loading using watermarks or change tracking.
- [ ] Schedule and orchestrate pipelines with SQL Server Agent, SSIS, or Azure Data Factory.
- [ ] Add automated unit and reconciliation tests.
- [ ] Publish a Power BI dashboard on top of the Gold layer.
- [ ] Add monitoring, logging, and alerting for failed loads.
- [ ] Containerize the local environment for easier setup.
- [ ] Extend the model with additional source systems and historical tracking.

---

## 🙏 Credits

This project was inspired by the SQL Data Warehouse learning content created by [Data With Baraa](https://www.youtube.com/@DataWithBaraa). Thank you for sharing practical, high-quality data-engineering education with the community.

---

## 👤 Author

**Muhamed**

[![GitHub](https://img.shields.io/badge/GitHub-Profile-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Muhamed-gad)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/muhamed-gad/)

> If you found this project useful, consider giving it a ⭐ on GitHub.
