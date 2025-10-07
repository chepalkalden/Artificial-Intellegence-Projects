# Artificial-Intellegence-Projects
# 🏥 US Health Care Claims C;assification
It is a Health Claim Categorization Project with Machine Learning

## 📌 Problem Statement

Health insurers receive millions of claims daily from hospitals, clinics, and pharmacies. These claims contain structured data such as diagnosis codes, procedure codes, provider types, and service dates. Categorizing these claims into types—**inpatient**, **outpatient**, and **pharmacy**—is essential for routing, adjudication, and analytics.

Manual categorization is slow and error-prone, leading to delays and incorrect processing. This project aims to automate claim classification using machine learning to improve accuracy and operational efficiency.

---

## 🎯 Project Goals

- Build a machine learning model to classify claims into predefined categories.
- Design a scalable ETL pipeline to ingest, clean, and prepare raw claim data.
- Engineer features that enhance model performance.
- Deliver a working ML pipeline that outputs categorized claims with high accuracy.

---

## 🛠️ ETL Pipeline Overview

### ✅ Goal
Ingest raw claim data, clean it, and prepare it for modeling.

### 🔹 Extract
Pull data from the data source mentioned below: For Claims Carrier, Inpatient, Outpatient and Drug Events the sample data has been downloaded and loaded by the ETL pipe line script from the Centers for Medicare & Medicaid Services site.

### 🔹 Transform
- Handle missing values
- Normalize categorical features (e.g., provider type, diagnosis codes)
- Encode dates (e.g., day of week, month, time gaps)
- Feature engineering (e.g., frequency of procedures, code groupings)

### 🔹 Load
Store cleaned data in a feature store or data warehouse for modeling and analysis.

---

## 📂 Data Sources

| Claim Type     | Download Link |
|----------------|---------------|
| Carrier Claims | [Download](http://downloads.cms.gov/files/DE1_0_2008_to_2010_Carrier_Claims_Sample_1A.zip) |
| Inpatient      | [Download](https://www.cms.gov/research-statistics-data-and-systems/downloadable-public-use-files/synpufs/downloads/de1_0_2008_to_2010_inpatient_claims_sample_1.zip) |
| Outpatient     | [Download](https://www.cms.gov/research-statistics-data-and-systems/downloadable-public-use-files/synpufs/downloads/de1_0_2008_to_2010_outpatient_claims_sample_1.zip) |
| Drug Events    | [Download](http://downloads.cms.gov/files/DE1_0_2008_to_2010_Prescription_Drug_Events_Sample_1.zip) |

📖 For dataset documentation, refer to the official [SynPUF Data Guide](https://www.cms.gov/research-statistics-data-and-systems/downloadable-public-use-files/synpufs/downloads/synpuf_dug.pdf).

---

## 🧠 Machine Learning Model

### 🔹 Dataset Construction
- Link cleaned datasets using the unique identifier `DESYNPUF_ID`.
- Merge **beneficiary**, **carrier**, **inpatient**, **outpatient**, and **drug** claims into a unified dataset.

### 🔹 Model Type
- **Multiclass Classification**

### 🔹 Algorithm
- **Random Forest Classifier**

### 🔹 Features
Selected based on correlation and domain relevance:
- Diagnosis codes (ICD)
- Procedure codes (CPT/HCPCS)
- Provider type
- Service dates
- Claim amount
- Location (if available)

### 🔹 Training Strategy
- Train/test split
- Cross-validation
- Optimization for accuracy, precision, and recall

---

## 📊 Outcome

- A fully functional ML pipeline that:
  - Ingests and processes raw claims
  - Classifies them into predefined categories
  - Outputs performance metrics and predictions
- Ready for deployment and integration into healthcare analytics platforms

---

## 🚀 Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/claim-categorization-ml.git
   cd claim-categorization-ml
