## Bronze Layer – Raw Data Ingestion

The Bronze layer is responsible for **ingesting raw source data** into the data lake
without applying any transformations. This layer serves as the **system of record**
and preserves the original structure and values of incoming datasets.

### 🔧 Implementation
- Orchestration tool: **Azure Data Factory**
- Source type: **HTTP endpoints**
- Storage: **Azure Data Lake Storage Gen2 (Bronze container)**
- Ingestion type: **Dynamic, parameter-driven pipelines**

### 🔄 Ingestion Strategy
- A single dynamic pipeline is used to ingest multiple datasets
- Dataset configuration is driven by a JSON parameter file
- Azure Data Factory uses:
  - Lookup activity to read parameters
  - ForEach activity to iterate over datasets
  - Copy activity to ingest data into the Bronze layer

### 📂 Files in This Layer
- `pipelines/dummy.json` – Parameter file containing source URLs and target paths
- `screenshots/` – Execution proof of pipeline creation and successful runs

### 📌 Key Characteristics
- Data is ingested **as-is**
- No cleansing, validation, or enrichment
- Enables traceability back to source systems
- Acts as the foundation for downstream transformations

> ⚠️ Azure resources were created using a free-tier subscription and decommissioned
> after pipeline validation to avoid ongoing costs. Screenshots are provided as proof.
