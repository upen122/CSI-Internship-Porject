# 📄 REPORT.md – Azure Data Factory Internship Project

##  What is this project about?

This project is part of the CSI Internship 2025, showcasing real-world use cases implemented using **Azure Data Factory**. It includes two major pipelines:
- A REST API ingestion pipeline for fetching country-specific data and storing it in **Azure Data Lake Storage Gen2**.
- A conditional data movement pipeline between **Azure SQL Database** and **ADLS**, with **modular pipeline execution** using parent-child logic and parameterization.

---

## What challenges were solved using ADF?

- Automated ingestion and storage of external API data.
- Conditional logic to copy data only when specific thresholds (e.g., record counts) were met.
- Modular design using **Execute Pipeline** activity and parameters.
- Dynamic file naming and path generation based on runtime data.

---

## Where dynamic handling was used?

- **Parameterized datasets** for dynamic country-based file generation.
- **Dynamic output file names** driven by record counts.
- Conditional **If activities** that control child pipeline execution.
- Use of **ForEach loops** with dynamically evaluated values.

---

##  What I learned

As a beginner to Azure, I initially struggled with:
- Setting up **Linked Services**, especially for REST and SQL sources.
- **Web activity usage** inside ForEach loops (which was later replaced with Copy Activity).
- Proper **parameter passing** and expression syntax.
- SQL Database **firewall rules** and **resource access restrictions**.
- Handling **nested conditions**, which Azure ADF doesn’t support directly—so I split logic into multiple branches.
- Connecting **child pipelines** with the correct parameter mapping.

These challenges helped me build a deep understanding of how to orchestrate and automate pipelines in Azure Data Factory.

---

##  What could be improved or added next?

- Implement **logging and error handling** using Stored Procedures or ADF diagnostics.
- Add **unit testing mechanisms** using Data Flow debug or mock datasets.
- Expand support for **more countries or APIs**.
- Introduce **Delta Lake ingestion** for incremental loading.
- Use **parameter files or config tables** to manage metadata-driven pipelines.
