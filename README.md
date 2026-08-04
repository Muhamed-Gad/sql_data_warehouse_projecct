# 🏗️ SQL Data Warehouse Project

A complete **SQL Data Warehouse** project that demonstrates how to design and build a modern Data Warehouse from scratch using SQL Server.

The project follows the Medallion Architecture (Bronze, Silver, and Gold layers) and implements a complete ETL pipeline, starting from raw CRM & ERP data to business-ready analytical models.

---

## 📌 Project Overview

This project covers the entire Data Warehouse development lifecycle, including:

- Designing the Data Warehouse Architecture
- Building ETL Pipelines
- Data Modeling
- Data Cleansing & Transformation
- Data Integration
- Data Quality Testing
- Creating a Business-ready Star Schema

The final output is a scalable SQL Data Warehouse optimized for reporting and analytics.

---

# 🎯 Project Objectives

- Build a SQL Data Warehouse from scratch.
- Integrate data from multiple business systems.
- Design a clean ETL pipeline.
- Apply Data Cleansing and Standardization techniques.
- Implement Medallion Architecture.
- Build analytical tables using Star Schema.
- Perform Data Quality Testing.

---

# 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| SQL Server | Database Engine |
| T-SQL | ETL & Data Transformation |
| Draw.io | Architecture & Data Modeling |
| Git | Version Control |
| GitHub | Project Hosting |

---

# 📂 Data Sources

The project integrates data from two different business systems.

## CRM Source

- Customer Information
- Product Information
- Sales Details

## ERP Source

- Customer Data
- Location Data
- Product Category
- Additional ERP Dimensions

---

# 🏛️ Data Warehouse Architecture

The project follows the Medallion Architecture.

## Bronze Layer

Purpose:

- Raw Data Ingestion
- Full Load Process
- Batch Processing
- Truncate & Insert Strategy

---

## Silver Layer

Purpose:

- Data Cleansing
- Data Standardization
- Data Normalization
- Derived Columns
- Data Enrichment

---

## Gold Layer

Purpose:

- Business Logic
- Data Integration
- Data Aggregation
- Flat Tables
- Star Schema
- Analytics-ready Data

---

# ⭐ Data Model

The Gold Layer contains:

### Dimension Tables

- gold.dim_customers
- gold.dim_products

### Fact Tables

- gold.fact_sales

These tables form a Star Schema optimized for reporting and Business Intelligence.

---
## Data Architecture

![Data Architecture](docs/data_architecture.png (https://github.com/Muhamed-Gad/sql_data_warehouse_projecct/blob/main/docs/Data%20Architecture.png))

## Data Flow Diagram

![Data Flow](docs/data_flow_diagram.png)

## Data Integration

![Data Integration](docs/data_integration.png)

## Star Schema

![Star Schema](docs/star_schema.png)



# 🔄 ETL Workflow

CRM + ERP Sources

⬇

Bronze Layer

⬇

Silver Layer

⬇

Gold Layer

⬇

Business Analytics

---

# 📊 Project Documentation

The project includes complete documentation inside the **docs** folder.

## Included Diagrams

- Data Architecture
- Data Flow Diagram
- Data Integration Diagram
- Star Schema

> Each diagram explains a different stage of the Data Warehouse design process.

---

# 📁 Repository Structure

```
SQL-Data-Warehouse-Project/

│
├── datasets/
│   ├── source_crm/
│   └── source_erp/
│
├── docs/
│   ├── Data Architecture
│   ├── Data Flow Diagram
│   ├── Data Integration
│   └── Star Schema
│
├── scripts/
│   ├── bronze/
│   │   ├── ddl.sql
│   │   └── proc_load_bronze.sql
│   │
│   ├── silver/
│   │   ├── ddl.sql
│   │   └── proc_load_silver.sql
│   │
│   └── gold/
│       ├── ddl.sql
│       └── proc_load_gold.sql
│
├── tests/
│   ├── silver/
│   └── gold/
│
└── README.md
```

---

# ✅ Data Quality Testing

Data validation scripts are included for:

- Silver Layer
- Gold Layer

The tests verify:

- Data Consistency
- Duplicate Records
- Missing Values
- Data Integrity
- Business Rules Validation

---

# 🚀 How to Run

1. Clone the repository.
2. Open SQL Server Management Studio.
3. Execute the Bronze Layer scripts.
4. Execute the Silver Layer scripts.
5. Execute the Gold Layer scripts.
6. Run the validation scripts.
7. Explore the Gold Layer tables.

---

# 📈 Project Highlights

✔ End-to-End Data Warehouse
✔ ETL Pipeline
✔ Medallion Architecture
✔ Star Schema
✔ SQL Server
✔ Data Integration
✔ Data Quality Testing
✔ Production-style Folder Structure

---

# 📚 Credits

This project was developed as part of the **SQL Data Warehouse** learning journey inspired by the excellent educational content created by **Data With Baraa**.
Special thanks to **Baraa** for providing the project idea, datasets, and detailed guidance throughout the course.
The implementation, repository organization, documentation, and GitHub publication were completed as part of my personal learning portfolio.

---

# 👨‍💻 Author
**Mohamed Gad**
Mechatronics Engineering Student
Aspiring Data Engineer | Data Analyst | AI Engineer

---
