# Source Code: End-to-End Modeling Pipeline

This directory contains the modularized Jupyter Notebooks used to build the Credit Risk Engine. To reproduce the results found in the Executive Summary, please execute the notebooks in the numbered order below.

## 🛠️ Execution Sequence

### 01_Data_Cleaning_and_Leakage_Prevention.ipynb
* **Purpose**: Performs initial data ingestion and filters for "finished" loan outcomes.
* **Key Operations**: Removes "Current" loans to prevent data leakage and maps the `target_default` variable.
* **Output**: A cleaned modeling dataset (`df_model`) ready for feature engineering.

### 02_Approval_Filter_Model.ipynb
* **Purpose**: Trains the Stage 1 "Gatekeeper" model to replicate historical approval policies.
* **Logic**: Uses a limited feature set (`loan_amnt`, `dti`, `emp_length`) to mimic initial screening.
* **Metric**: Optimized for high AUC-ROC (~0.96) to ensure policy alignment.

### 03_Default_Risk_Engine.ipynb
* **Purpose**: The core risk assessment model for approved applicants.
* **Key Operations**: Implements stratified splitting (70/15/15) and handles class imbalance using XGBoost `scale_pos_weight`.
* **Metric**: Evaluated on a hold-out test set with a focus on AUC-ROC (0.7042) and Precision-Recall.

### 04_Explainability_and_Threshold_Tuning.ipynb
* **Purpose**: Translates model probabilities into business decisions.
* **Key Operations**: Generates SHAP global and local force plots for regulatory transparency.
* **Analysis**: Conducts the threshold sweep to identify the optimal 0.45 cutoff for maximizing default capture.

---

## 📦 Dependencies
Ensure you have the following libraries installed before running the notebooks:
* `pandas`, `numpy`
* `scikit-learn`
* `xgboost`
* `shap`
* `matplotlib`, `seaborn`
