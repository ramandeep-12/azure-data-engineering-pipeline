## Silver Layer – Data Transformation

The Silver layer is responsible for **cleaning, standardizing, and transforming**
raw data ingested in the Bronze layer. This layer produces **curated datasets**
suitable for analytical processing.

### 🔧 Implementation
- Processing engine: **Azure Databricks**
- Language: **PySpark**
- Input: Bronze layer data
- Output: Silver layer datasets in Azure Data Lake

### 🔄 Transformation Logic
Transformations implemented in this layer include:
- Schema normalization
- Data type casting
- Column standardization
- Removal of inconsistencies
- Basic data enrichment

### 📂 Files in This Layer
- `transformations/silver_layer.py` – PySpark script implementing transformations
- `screenshots/` – Databricks workspace, cluster, and notebook execution proof

### 📌 Key Characteristics
- Separates raw ingestion from transformation logic
- Ensures data quality and consistency
- Prepares data for analytics and serving layers
- Supports reprocessing and scalability

> Physical Silver datasets are not stored in this repository, as transformations
> were executed in Azure Databricks. The transformation logic and screenshots
> represent the core implementation.
