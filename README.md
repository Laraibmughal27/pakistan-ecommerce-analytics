# 📊 Pakistan Largest E-Commerce Dataset: Exploratory Data Analysis & Business Intelligence

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Cleaning-orange.svg)](https://pandas.pydata.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📌 Business Overview
This repository contains a comprehensive **Data Cleaning and Exploratory Data Analysis (EDA)** workflow focusing on Pakistan's largest e-commerce transactional dataset. Operating from a data-driven framework, this project tackles data pipeline anomalies, builds robust text/date schemas, models net sales adjusted for operational friction, and provides strategic recommendations to improve top-line order fulfillment and marketing investments.

---

## 🛠️ Data Pipeline & Technical Architecture
The data pipeline is designed explicitly using core **Python Pandas** frameworks, emphasizing high efficiency and explicit code execution targeted at commercial data auditing. 

### Key Technical Operations Performed:
1. **Low-Memory Batch Ingestion:** Handled high-volume transaction files safely using segmented memory constraints (`low_memory=False`).
2. **Missing Value Auditing & Handling:** Implemented strategic structural labeling (`.fillna('missing')`) across high-frequency text categories like SKU varieties, payment channels, and sales commission identifiers to prevent group aggregation failures.
3. **Operational Schema Alignment:** Fixed unstructured timestamps and text streams into executable data structures:
   * String date conversion (`pd.to_datetime`) with error coercion (`errors='coerce'`).
   * Generated explicit date hierarchies (Order Year, Order Month-Period, Weekday strings) for predictive calendar patterns.
   * Converted textual currencies and counts into accurate numeric fields (`to_numeric`).
4. **Business-Logic Revenue Correction:** Built a customized data column separating raw gross revenue from true transactional performance by tracking lower-case cancellations and refund states via string masking.
5. **Efficiency Engineering:** Calculated processing gaps (the duration between order creation and execution) to identify delivery workflow bottlenecks.

---

## 📈 Key Analysis Fields Implemented
The accompanying notebook systematically walks through several operational tables:
* **Order Status Frequency & Financial Impacts:** Identifying which customer statuses (e.g., Cancelled, Refunded, Complete) leak the most revenue.
* **Temporal Sales Velocities:** Extracting annual trends, seasonal monthly spikes, and high-frequency purchasing weekdays to direct target marketing campaigns.
* **AOV Metric Development:** Generating Monthly Average Order Value (AOV) trackers to distinguish if revenue spikes are driven by expensive order segments or higher unit volumes.
* **Operational Friction Trackers:** Evaluating distribution and manufacturing fulfillment delays across specific transaction blocks.

---

## ⚠️ Analytical Guardrails & Data Limitations
To ensure transparency and high-level analytical integrity, this pipeline accounts for the following data limitations present in the raw source:
* **Geographical Constraints:** The dataset omits city and provincial labels, preventing true geographic cluster segmentation.
* **Margin Approximation:** Real unit economics (shipping overhead, acquisition costs, supplier margins) were absent. Financial estimates assume a safe 70% product cost overhead floor to establish a baseline for business profit planning rules.

---

## 🚀 How To Run This Project

### 1. Clone the Workspace
```bash
git clone [https://github.com/YOUR_USERNAME/pakistan-ecommerce-analytics.git](https://github.com/YOUR_USERNAME/pakistan-ecommerce-analytics.git)
cd pakistan-ecommerce-analytics
