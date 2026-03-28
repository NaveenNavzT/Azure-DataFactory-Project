# 🚀 Azure Data Factory Project

## 📌 Overview
This project demonstrates an end-to-end data engineering pipeline using Azure Data Factory, implementing a Medallion Architecture (Bronze, Silver, Gold layers) on Azure Data Lake.

---

## 🥉 Bronze Layer (Raw Data Ingestion)

- Built a dynamic pipeline using **ForEach** and **Copy Activity** to ingest multiple CSV files from the Source folder into the Bronze container in Azure Data Lake.  
  **Datasets:** DimAirline, DimPassenger, DimFlight  

- Developed an API-based pipeline to ingest JSON data from GitHub into the Bronze container.  
  **Dataset:** DimAirport  

- Implemented an incremental load pipeline using Azure SQL, based on the **last updated timestamp**, and stored data in **Parquet format**.  
  **Dataset:** FactBooking  

- Created a parent pipeline using **Execute Pipeline Activity** to orchestrate all ingestion processes.  

- Integrated an alerting mechanism using **Azure Logic Apps** to send email notifications on pipeline execution status.  

---

## 🥈 Silver Layer (Data Transformation)

- Designed Data Flows to perform multiple transformations:
  - Filtering  
  - Column derivation  
  - Data standardization (lower/upper case)  
  - Schema alignment  

- Implemented **upsert logic** and stored processed data as **Delta format** in the Silver container.  

- **Processed datasets:**
  - DimAirline  
  - DimPassenger  
  - DimFlight  
  - FactBooking  

---

## 🥇 Gold Layer (Business-Level Data)

- Built final business views by joining fact and dimension tables using Data Flows.  

- Applied advanced transformations:
  - Join operations  
  - Filtering  
  - Window functions (**Dense Rank**) to identify:
    - Top-performing airlines  
    - Top passengers  
    - Most active flights  

- Integrated project with Azure DevOps:
  - Published pipelines as **ARM Template JSON files**  
  - Enabled version control and **CI/CD readiness**  

---
