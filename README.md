# 🚖 Azure NYC Taxi Data Engineering Pipeline

This repository presents a **comprehensive end-to-end Data Engineering project** built on the **NYC Taxi dataset**, using **Azure Data Factory, Azure Data Lake Storage, Databricks (PySpark + Delta Lake), and Power BI**.  
The project is designed to **mimic real-world industry workflows** by implementing the **Medallion Architecture (Bronze → Silver → Gold)**, ensuring scalability, automation, and security.

---

## 📌 Project Summary
This project focuses on building a **modern cloud-based data platform** where data is dynamically ingested, transformed, and made analytics-ready through structured layers.  

### Key Features:
- 🚀 **Dynamic Data Ingestion**: Automated pipelines in **Azure Data Factory (ADF)** pull data directly from **web APIs**, eliminating manual uploads.  
- 🏗️ **Medallion Architecture**: Data is processed in layered stages (Bronze → Silver → Gold) to ensure quality, governance, and scalability.  
- 🔥 **Big Data Transformations**: Use of **PySpark in Databricks** to handle large volumes of raw taxi data.  
- 💎 **Delta Lake Optimization**: Transforming silver data into **Delta format** for ACID transactions, schema enforcement, and time-travel queries.  
- 📊 **Visualization**: Serving final curated data to **Power BI dashboards** for insights and analytics.  
- 🔐 **Security**: Leveraging **Managed Identities & Service Principals** to enforce enterprise-grade authentication.  

---

## 🏗️ Project Architecture
![Project Architecture](architecture/azure_medallion_architecture.png)

The project follows the **Medallion Architecture**:  

1. **Bronze Layer (Raw Ingestion)**  
   - Data ingested directly from **NYC Taxi APIs** using **ADF pipelines**.  
   - Stored as **raw parquet files** in **Azure Data Lake Storage Gen2 (ADLS)**.  
   - Pipelines are **parameterized & dynamic**, iterating month-by-month automatically.  

2. **Silver Layer (Cleansed & Transformed)**  
   - Raw data processed in **Databricks (PySpark)**.  
   - Applied transformations:  
     - Handling missing/invalid values  
     - Date/time conversions  
     - Complex data splits  
     - Schema alignment  
   - Output stored back in **ADLS (Parquet format)**.  

3. **Gold Layer (Analytics-Ready)**  
   - Data converted to **Delta Tables** for optimized querying.  
   - Implemented:  
     - ACID compliance   
     - Schema enforcement  
     - **Time Travel** (querying past versions of data)  
   - Final curated tables are directly consumed by **Power BI** for reporting.  

---

## 🔄 Workflow Walkthrough

### 1️⃣ Data Ingestion with ADF
- Parameterized ADF pipeline automatically ingests multiple months of taxi trip data.  
- Copy activity fetches data from **NYC API** → stores in **Bronze Layer (ADLS)**.  
- **Dynamic content + ForEach loop** ensures scalability without manual intervention.  

### 2️⃣ Bronze → Silver (Transformation in Databricks)
- Databricks notebooks (PySpark) read raw parquet files.  
- Applied transformations:  
  - Filter out corrupt/missing rows  
  - Standardize datetime columns (pickup, dropoff)  
  - Convert categorical values to meaningful labels  
  - Partition by year/month for optimized queries  
- Transformed output stored in **Silver Layer (Parquet)**.  

### 3️⃣ Silver → Gold (Delta Lake Optimization)
- Silver tables upgraded to **Delta format**.  
- Delta features used:  
  - **Transaction log** for ACID compliance  
  - **Time Travel** to query historical versions  
  - **Schema evolution** for changing data sources  
  - **Incremental MERGE** for updates  
- Gold data made **query-efficient and BI-ready**.  

### 4️⃣ Visualization in Power BI
- Gold Delta tables connected to **Power BI** via **Azure Databricks Connector**.  
- Interactive dashboards built for:  
  - Trip volume analysis  
  - Revenue trends  
  - Pickup/drop-off hotspots  
  - Monthly comparisons  

---

## 🛠️ Tech Stack
- **Azure Data Factory (ADF)** → Orchestration & API ingestion  
- **Azure Data Lake Storage Gen2 (ADLS)** → Scalable storage  
- **Databricks (PySpark)** → Data cleansing & transformation  
- **Delta Lake** → ACID transactions, time travel, schema evolution  
- **Azure Active Directory (AAD)** → Security (Managed Identities & Service Principals)  
- **Power BI** → Visualization & analytics  

