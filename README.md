# Azure End-to-End Data Engineering Pipeline (Medallion Architecture)

## 📌 Overview
This project demonstrates an end-to-end **Azure Data Engineering pipeline** built using
Azure Data Factory, Azure Data Lake Gen2, Azure Databricks, Azure Synapse Analytics,
and Power BI.

The goal was to ingest raw data from an external source, process it using
a **Medallion Architecture (Bronze → Silver → Gold)**, and serve analytics-ready
data for reporting and visualization.

> ⚠️ Note: Azure resources were created using a **free-tier account**.
> Screenshots and documentation are provided as execution proof.

---

## 🧱 Architecture
**Medallion Architecture**
- **Bronze**: Raw data ingestion (no transformation)
- **Silver**: Cleaned & enriched data (Databricks)
- **Gold**: Business-ready datasets (Synapse views & external tables)

📷 See architecture diagram: `architecture/architecture-diagram.png`

---

## 🛠️ Tech Stack
- Azure Data Factory (ETL Orchestration)
- Azure Data Lake Storage Gen2
- Azure Databricks (PySpark)
- Azure Synapse Analytics (Serverless SQL)
- Power BI
- Python, SQL

---

## 🔄 Data Pipeline Flow

### 1️⃣ Data Ingestion (Bronze Layer)
- Used **Azure Data Factory**
- Ingested CSV data from an HTTP source (GitHub)
- Stored raw data in **Bronze container**
- Implemented:
  - Static pipeline
  - Dynamic pipeline using Lookup + ForEach + parameterization

📷 Proof: `screenshots/adf_pipeline_success.png`

---

### 2️⃣ Data Transformation (Silver Layer)
- Used **Azure Databricks**
- Read raw data from Bronze layer
- Applied:
  - Data cleaning
  - Schema normalization
  - Basic transformations
- Output written to **Silver container**

📷 Proof: `screenshots/databricks_notebook.png`

---

### 3️⃣ Data Serving (Gold Layer)
- Used **Azure Synapse Analytics (Serverless SQL Pool)**
- Created:
  - Views on Silver data using `OPENROWSET`
  - External tables using **CETAS**
- Implemented Lakehouse concept (Data Lake + SQL abstraction)

📷 Proof: `screenshots/synapse_views.png`

---

### 4️⃣ Analytics & Visualization
- Connected **Power BI** to Synapse Serverless SQL endpoint
- Built dashboards on Gold-layer datasets
- Enabled business-level reporting

📷 Proof: `powerbi/dashboard-screenshots/`

---

## 📂 Repository Contents
- `pipelines/` → ADF pipeline documentation
- `databricks/` → PySpark transformation scripts
- `synapse/` → SQL scripts for views & external tables
- `screenshots/` → Execution proof
- `docs/` → Step-by-step Azure setup documentation

---

## 💡 Key Learnings
- End-to-end ETL design on Azure
- Medallion Architecture implementation
- Dynamic pipelines with parameterization
- Lakehouse design using Synapse Serverless SQL
- Cost-aware development using free-tier resources

---

## 🚀 Why This Project Matters
This project mirrors **real-world Data Engineering workflows** used in production
analytics systems and demonstrates practical experience with Azure cloud services,
pipeline orchestration, and analytical data modeling.
