## Raw Data (Source Layer)

This folder contains **raw source datasets** used in the Azure Data Engineering pipeline.
The data is part of the **AdventureWorks** dataset and represents the **initial input**
to the Medallion Architecture.

### 📌 Purpose of Raw Layer
- Acts as the **source system representation**
- Data is kept **unchanged and immutable**
- No cleaning, transformation, or validation is applied at this stage
- Serves as the input for ingestion into the **Bronze layer**

### 📂 Data Description
The raw datasets include representative CSV files such as:
- Customers
- Products
- Sales
- Calendar
- Territories

These files simulate data coming from external systems (e.g., APIs or file-based sources).

### 🔄 Ingestion Flow
- Azure Data Factory reads these datasets using an **HTTP linked service**
- Dataset ingestion is dynamically controlled using a **JSON parameter file**
- Data is landed into the **Bronze container** in Azure Data Lake Storage Gen2

### ⚠️ Note
Only representative raw files are included in this repository to keep it lightweight.
In the actual pipeline execution, multiple related datasets were ingested using the
same dynamic ingestion pattern.

This folder exists to document the **source data structure**, not to store processed outputs.
