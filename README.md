# End-to-End-Scanpy-Pipeline-for-GSE145926-Automated-HDF5-Ingestion-Interactive-Plotly-Analysis
End-to-End Scanpy Pipeline for GSE145926: Automated HDF5 Ingestion &amp; Interactive Plotly Analysis
# 🧬 End-to-End Scanpy Pipeline for GSE145926: Automated HDF5 Ingestion & Interactive Plotly Analysis

This repository contains a robust, fully automated bioinformatics pipeline for analyzing Single-Cell RNA Sequencing (scRNA-seq) data. It is specifically tailored for the **COVID-19 Bronchoalveolar Lavage Fluid (BALF)** dataset (**GSE145926**), originally published by *Liao et al. (Nature Medicine, 2020)*.

The workflow addresses common challenges in public data analysis, such as automated fetching from NCBI GEO, handling HDF5 (`.h5`) formats, batch correction, and providing interactive visualizations for data exploration.

## 🚀 Key Features

* **🔄 Automated Data Ingestion Engine:**
    * Directly connects to NCBI GEO FTP servers.
    * Auto-downloads the raw tarball (~250MB).
    * Extracts and intelligently identifies **HDF5 (.h5)** sample files using Regex.
    * **Smart Caching:** Prevents re-downloading if data exists locally.
* **🧩 Robust Data Handling:**
    * Merges multiple patient samples into a single `AnnData` object.
    * Handles unique variable naming collisions during concatenation.
* **📊 Lung-Specific QC & Filtering:**
    * Customized filtering thresholds adapted for BALF tissue samples (Relaxed Mitochondrial cutoff at 20%).
* **📈 Interactive Visualization:**
    * Integrated **Plotly** charts for QC metrics, HVG selection, UMAP clustering, and Marker Gene expression.
    * Zoom, pan, and hover capabilities for deep data inspection.

## 🛠️ Installation & Prerequisites

To run this notebook, you need Python 3.8+ and the following bioinformatics libraries:

```bash
pip install scanpy leidenalg plotly pandas matplotlib seaborn scipy requests
