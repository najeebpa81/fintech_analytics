# Technical Methodology: Credit Risk Pipeline

## 1. Project Philosophy: The Two-Gate System
To simulate a real-world banking environment, this project utilizes a sequential modeling approach:
* **Gate 1 (Approval Filter):** Replicates the current business policy to identify "Acceptable" applicants based on basic criteria (`loan_amnt`, `dti`, `emp_length`).
* **Gate 2 (Default Risk Engine):** Conducts a deep-dive risk assessment on approved loans using 40+ engineered features to calculate the Probability of Default (PD).

## 2. Data Integrity & Leakage Prevention
A critical step in this pipeline was the strict filtering of the dataset to prevent "Data Leakage":
* **Exclusion of 'Current' Loans:** Only loans with a definitive outcome ("Fully Paid" or "Charged Off") were used for training the Default Risk Model. 
* **Rationale:** Including "Current" loans (which are still in progress) would introduce noise and bias, as their final status is unknown.
* **Target Alignment:** The target variable `target_default` was mapped specifically from "Charged Off" status to ensure the model learns the exact characteristics of a default event.



## 3. Class Imbalance Strategy
The training set exhibited a moderate imbalance (~20% defaults). 
* **Technique:** We utilized XGBoost’s `scale_pos_weight` parameter, calculated as the ratio of negative to positive classes.
* **Impact:** This ensures the model places higher importance on correctly identifying the minority "Default" class without requiring artificial oversampling (SMOTE).

## 4. Model Selection & Tuning
* **Algorithm:** XGBoost was chosen for its ability to handle non-linear relationships and missing values inherently.
* **Optimization:** The model was optimized for **AUC-ROC** to maximize the ranking separation between good and bad borrowers.
