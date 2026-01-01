# Source Code: End-to-End Predictive Model

This directory contains the primary codebase for the Credit Risk Pipeline. The project is contained within a single, comprehensive Jupyter Notebook to ensure a seamless narrative flow from data ingestion to model deployment strategies.

## 🛠️ Main Notebook: `Predictive_Model_Loan_Approval.ipynb`

This notebook follows a systematic 14-step process to build a professional-grade credit engine:

1.  **Data Ingestion & Integrity**: Loading Lending Club data and filtering for finished loan outcomes to prevent target leakage.
2.  **Gate 1 (Approval Filter)**: Developing a replication model of historical approval policies using core application features.
3.  **Feature Engineering**: Processing 40+ behavioral and financial features for Stage 2 modeling.
4.  **Gate 2 (Default Risk Engine)**: Training an XGBoost classifier with stratified splits and class weighting (`scale_pos_weight`).
5.  **Model Explainability**: Implementing SHAP to identify global risk drivers (Grade, Int Rate, DTI) and local prediction justifications.
6.  **Performance Evaluation**: Measuring success via AUC-ROC (0.7042) and Precision-Recall analysis.
7.  **Threshold Optimization**: Calculating the optimal 0.45 cutoff to maximize default capture while maintaining loan volume.

---

## 📦 Dependencies
To run this notebook, install the following packages:
* `pandas` & `numpy`: Data manipulation.
* `scikit-learn`: Data splitting and evaluation metrics.
* `xgboost`: Gradient boosted decision trees.
* `shap`: Model interpretability.
* `matplotlib` & `seaborn`: Visualization.
