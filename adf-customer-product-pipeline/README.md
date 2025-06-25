# 🔄 Azure Data Factory – Customer & Product Conditional Copy Pipeline

## 📌 Task Overview

This solution contains two connected pipelines that handle conditional data transfer from an Azure SQL Database to Azure Data Lake (ADLS):

1. ✅ Copy **Customer** data to ADLS **if record count > 500**  
2. 🔁 If **Customer count > 600**, trigger a **Child Pipeline** to copy **Product** data  
3. 📦 Data is stored in ADLS as **JSON** files  

---

## 🏗️ Pipeline Architecture

### 🔹 Main Pipeline Logic

- Performs a **Lookup** to get the customer record count.
- Uses **IfCondition** to validate `count > 500`
- Executes **CopyCustomerData** if condition is met.
- Triggers **ChildPipeline** if count exceeds 600, passing the count via **pipeline parameter**.

### 🔹 Child Pipeline Logic

- Accepts `customerCount` from parent pipeline.
- Performs **Lookup** on product records.
- If product count > 0, copies the data to ADLS.
- Uses dynamic parameter to name the product file like:  
  `product_data_{customerCount}.json`

---

## 🧩 Visual Flow – Main Pipeline

![Main Pipeline View](./Main_pipeline.png)

---

## 🧩 Visual Flow – Child Pipeline

![Child Pipeline View](./Child_pipeline.png)

---

## 📂 Output Files in ADLS

> The following files are dynamically created in ADLS Gen2:

- `customer_data.json`
- `product_data_610.json` (example when customer count is 610)

![Output Screenshot](./Output.png)

---

## ⚙️ Trigger (Optional)

If using scheduled automation, attach a trigger to run daily or based on another event.

---

## 🧠 Technical Details

| Component              | Value / Description                                |
|------------------------|----------------------------------------------------|
| **Main Pipeline**      | `CopyCustomerDataPipeline`                         |
| **Child Pipeline**     | `ChildPipeline`                                    |
| **Source DB**          | Azure SQL Database                                 |
| **Sink**               | Azure Data Lake Storage (ADLS Gen2)                |
| **Format**             | JSON                                               |
| **Trigger Condition**  | `CustomerCount > 500` & `CustomerCount > 600`      |
| **File Naming**        | Static for customer; Dynamic for product files     |
| **Parameter Passing**  | `pipeline().parameters.customerCount`              |

---

## 📄 JSON Pipeline Definitions

You can explore full ADF pipeline definitions here:

- 🔗 [Main Pipeline JSON](./Main_pipeline.json)
- 🔗 [Child Pipeline JSON](./Child_pipeline.json)

Make sure these files are committed to the repo at the same level as this README.

---

## ✅ Status

- ✔️ Successfully implemented conditional logic  
- ✔️ Parent-child pipeline parameter passing validated  
- ✔️ ADLS storage tested and file naming verified  

---

## 👨‍💻 Developed By

**Upen Singh**  
📧 `upensingh799@gmail.com`  
🎓 CSI Internship Project 2025

---

