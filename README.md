# CRC-Patient-Survival-Prediction

# Colorectal Cancer Patient Survival Prediction Using TabNet Model

[![DOI](xxx)](xxx)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

This repository contains the official implementation code for the paper:
**"Colorectal Cancer Patient Survival Prediction Using TabNet Model"**

Presented at the *2025 International Conference on Information and Communication Technology and Applications (ICICTyA)*.

## 📌 Project Overview

Colorectal cancer (CRC) survival prediction is a critical task for optimizing clinical decision-making. However, many high-performing machine learning models function as "black boxes," hindering their adoption in medical settings.

This study develops an **interpretable deep learning model** using **TabNet** to predict the survival status (Alive/Dead) of CRC patients. By leveraging a comprehensive dataset from the **SEER Program** (2018-2022), our approach combines robust predictive accuracy with native explainability.

### Key Features:
* **TabNet Architecture:** Utilizes sequential attention for instance-wise feature selection.
* **Imbalance Handling:** Implements **Edited Nearest Neighbors (ENN)** resampling to effectively address class imbalance.
* **Optimized Performance:** Achieves superior **Macro F1-Score (0.7710)** and **AUC (0.8885)** compared to standard baselines.
* **Interpretability:** Provides global and local feature importance analysis, identifying **Primary Site**, **Clinical Grade**, and **Nodal Status** as key predictors.

## 📂 Dataset Access

The dataset used in this study is sourced from the **Surveillance, Epidemiology, and End Results (SEER) Program**.

* **Source:** NCI SEER 17-Registries Research Data (Nov 2023 Submission).
* **Cohort:** Patients diagnosed with CRC between 2018-2022.
* **Inclusion Criteria:** `Primary Site` (180-209), `Histologic Type ICD-O-3` (8000-9000).
* **Access Policy:** Due to the Data-Use Agreement (DUA), **we cannot distribute the raw data directly in this repository.** Researchers must request access directly from the official SEER website.
    * [Request SEER Data Access](https://seer.cancer.gov/data/access.html)


## 🛠️ Installation & Requirements

To reproduce the results, it is recommended to use a virtual environment (e.g., conda or venv).

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/username/repo-name.git](https://github.com/username/repo-name.git)
    cd repo-name
    ```

2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

**Key Dependencies:**
* `pytorch-tabnet>=4.1.0`
* `torch>=2.0.0`
* `scikit-learn>=1.2.2`
* `imbalanced-learn>=0.10.1`

## 🚀 Usage Instructions

The entire experimental pipeline is consolidated into a single Jupyter Notebook for ease of reproduction.

### 1. Open the Notebook
Navigate to `notebooks/CRC_Survival_Prediction_TabNet.ipynb` (or the name of your file).

### 2. Run the Pipeline
Execute the cells sequentially. The notebook performs the following steps in order:

* **Step 1: Data Preprocessing** (Cleaning, Filtering, Label Encoding)
* **Step 2: Hyperparameter Tuning** (Randomized Search CV on imbalanced data)
* **Step 3: Resampling Comparison** (Evaluating SMOTE, ENN, SMOTE-ENN vs Baseline)
* **Step 4: Final Model Training** (Training TabNet with ENN and optimal parameters)
* **Step 5: Evaluation & Interpretation** (Confusion Matrix, DeLong Test, Feature Importance)

## 📊 Model Card & Reproducibility

### Model Configuration
To ensure exact replication, use the following configuration found in our experiments:

* **Random Seed:** `42`
* **Optimal Hyperparameters:**
    ```json
    {
      "n_d": 16,
      "n_a": 10,
      "n_steps": 6,
      "gamma": 1.0,
      "lambda_sparse": 0.000149,
      "optimizer_params": {"lr": 0.0089},
      "mask_type": "entmax"
    }
    ```
* **Preprocessing:** Label Encoding for categorical features; ENN resampling for the training set.

### Performance Metrics (Test Set)

| Metric | Value | 95% CI (Bootstrap) |
| :--- | :--- | :--- |
| **AUC-ROC** | 0.8885 | 0.8803 – 0.8975 |
| **Macro F1-Score** | 0.7710 | 0.7599 – 0.7825 |
| **Accuracy** | 86.50% | - |
| **PR-AUC (Dead Class)**| 0.3093 | 0.2885 – 0.3301 |
| **Brier Score** | 0.1020 | - |

## 📜 Citation

If you use this code or our findings in your research, please cite our paper:

```bibtex
@inproceedings{Damayanti2025TabNet,
  title={Colorectal Cancer Patient Survival Prediction Using TabNet Model},
  author={Rezki Yulia Damayanti and Untari Novia Wisesty and Rita Rismala},
  booktitle={2025 International Conference on Information and Communication Technology and Applications (ICICTyA)},
  year={2025},
  organization={IEEE}
}
