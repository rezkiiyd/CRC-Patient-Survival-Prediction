# 📂 Dataset Information

**⚠️ IMPORTANT: Raw Data Not Included**

Due to the **Data-Use Agreement (DUA)** with the National Cancer Institute (NCI), we are **not permitted** to distribute the raw SEER data directly in this repository.

To reproduce the experiments, researchers must request access and download the data directly from the official source.

## 1. Data Source
* **Program:** Surveillance, Epidemiology, and End Results (SEER) Program.
* **Database:** SEER 17-Registries Research Data (November 2023 Submission).
* **Link:** [Request SEER Data Access](https://seer.cancer.gov/data/access.html)

## 2. How to Obtain the Data
1.  **Register:** Sign the SEER Data-Use Agreement and obtain a username/password.
2.  **Software:** Download and install the **SEER*Stat** software.
3.  **Selection Criteria:** Create a "Case Listing Session" in SEER*Stat with the following filters to match our cohort:
    * **Site Recode:** Colon and Rectum.
    * **Year of Diagnosis:** 2018 - 2022.
4.  **Export:** Export the results as a CSV file (comma-delimited).

## 🧬 Feature Description

The dataset consists of 34 columns, including the target variable. Below is the complete list of features:

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `Patient ID` | `int64` | Unique identifier for each patient (removed during preprocessing). |
| `Age (15-90+)` | `object` | Patient's age group at diagnosis (e.g., '15-19 years', '90+ years'). |
| `Race recode (White, Black, Other)` | `object` | Patient's race category. |
| `Sex` | `object` | Patient's gender ('Male' or 'Female'). |
| `Year of diagnosis` | `int64` | The year the cancer was diagnosed (2018-2022). |
| `Marital status at diagnosis` | `object` | Marital status of the patient at the time of diagnosis. |
| `Primary Site` | `int64` | Code representing the specific location of the tumor in the colon/rectum. |
| `Histologic Type ICD-O-3` | `int64` | Code for the specific type of tissue/cell where cancer began. |
| `Behavior code ICD-O-3` | `object` | Behavior of the tumor (e.g., 'Malignant'). |
| `Diagnostic Confirmation` | `object` | Method used to confirm the cancer diagnosis (e.g., 'Positive histology'). |
| `Chemotherapy recode (yes, no/unk)` | `object` | Indicates if chemotherapy was performed. |
| `Radiation recode` | `object` | Indicates if radiation therapy was performed. |
| `Derived Summary Grade 2018 (2018+)` | `object` | Grade of the tumor (differentiation level). |
| `RX Summ--Surg Prim Site (1998+)` | `int64` | Code for the type of surgery performed on the primary site. |
| `RX Summ--Surg/Rad Seq` | `object` | Sequence of radiation and surgery therapy. |
| `Time from diagnosis to treatment` | `object` | Time interval (days) between diagnosis and treatment start. |
| `Regional nodes positive (1988+)` | `int64` | Number of regional lymph nodes examined that were positive for cancer. |
| `SEER Combined Mets at DX-bone` | `object` | Presence of bone metastasis at diagnosis. |
| `SEER Combined Mets at DX-liver` | `object` | Presence of liver metastasis at diagnosis. |
| `SEER Combined Mets at DX-lung` | `object` | Presence of lung metastasis at diagnosis. |
| `Derived EOD 2018 T Recode (2018+)` | `object` | Extent of the primary tumor (T stage). |
| `Derived EOD 2018 N Recode (2018+)` | `object` | Extent of spread to regional lymph nodes (N stage). |
| `Derived EOD 2018 M Recode (2018+)` | `object` | Extent of distant metastasis (M stage). |
| `EOD Primary Tumor Recode (2018+)` | `int64` | Detailed coding for primary tumor extent. |
| `EOD Regional Nodes Recode (2018+)` | `int64` | Detailed coding for regional lymph node involvement. |
| `EOD Mets Recode (2018+)` | `int64` | Detailed coding for distant metastasis. |
| `Median household income` | `object` | Median household income of the patient's area (inflation adjusted). |
| `Rural-Urban Continuum Code` | `object` | Code indicating the rural-urban status of the patient's residence. |
| `First malignant primary indicator` | `object` | Indicates if this is the patient's first primary cancer. |
| `Derived EOD 2018 Stage Group` | `object` | Overall cancer stage group (0-IV) derived from EOD fields. |
| `Grade Pathological (2018+)` | `object` | Pathological grade of the tumor. |
| `Grade Clinical (2018+)` | `object` | Clinical grade of the tumor. |
| `Tumor Size Summary (2016+)` | `int64` | Size of the tumor in millimeters. |
| `SEER cause-specific death` | `object` | **Target Variable**: 'Alive or dead of other cause' vs 'Dead (attributable to this cancer dx)'. |

*Refer to the main `README.md` or the preprocessing notebook for the full list of features.*
