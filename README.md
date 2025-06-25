# 🚀 Azure Data Factory Project – CSI Internship 2025

This repository contains multiple Azure Data Factory (ADF) pipelines demonstrating data integration, transformation, and automation using Azure services.

---

## 📁 Project Modules

### 1️⃣ [🌍 Country Data Pipeline](./CountryPipeline/README.md)
- Fetches data from a REST API for selected countries (India, US, UK, China, Russia).
- Saves each country's data as individual `.json` files in Azure Data Lake Storage (ADLS).
- Triggered automatically **twice daily** (12:00 AM & 12:00 PM IST).

➡️ [View Detailed Documentation](./CountryPipeline/README.md)

---

### 2️⃣ [🔄 Conditional Copy Pipeline](./CustomerProductPipeline/README.md)
- Copies customer data from Azure SQL Database to ADLS **if record count > 500**.
- Triggers a **Child Pipeline** to copy product data **if count > 600**, passing a parameter.
- Output filenames are dynamically generated based on record counts.

➡️ [View Detailed Documentation](./CustomerProductPipeline/README.md)

---

## 🧰 Tech Stack

- **Azure Data Factory**
- **Azure Data Lake Storage Gen2**
- **Azure SQL Database**
- **REST APIs**
- **JSON & Parameterized Datasets**
- **Pipeline Triggers & Conditional Logic**

---

## 🧠 Learning Outcomes

- ADF orchestration & automation
- Dynamic pipeline creation using parameters
- Data movement from APIs and SQL to ADLS
- Conditional logic & modular pipeline design

---

## 👨‍💻 Developed By

**Upen Singh**  
📧 `upensingh799@gmail.com`  
🎓 CSI Internship 2025

---

## 📌 Folder Structure

