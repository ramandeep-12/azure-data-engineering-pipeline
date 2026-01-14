## Gold Layer – Analytics & Data Serving

The Gold layer represents **business-ready, analytics-optimized data** used for
reporting and visualization. This layer is designed for consumption by BI tools
and stakeholders.

### 🔧 Implementation
- Analytics engine: **Azure Synapse Analytics**
- SQL Pool: **Serverless SQL Pool**
- Storage: **Azure Data Lake Storage Gen2**
- Consumption tool: **Power BI**

### 🔄 Serving Strategy
- Views are created on top of Silver layer data using `OPENROWSET`
- External tables are created using **CETAS (Create External Table As Select)**
- Implements the **Lakehouse architecture** combining Data Lake and SQL analytics

### 📂 Files in This Layer
- `sql/create_views_gold.sql` – SQL scripts for business-level views
- `sql/external_table.sql` – CETAS scripts for external tables
- `screenshots/` – Synapse SQL execution and Power BI connection proof

### 📌 Key Characteristics
- Optimized for reporting and dashboards
- Abstracts storage complexity from consumers
- Enables scalable analytics without data duplication
- Supports direct BI connectivity

> Gold layer datasets were validated using Synapse Serverless SQL and consumed
> in Power BI. Execution proof is provided via screenshots.
