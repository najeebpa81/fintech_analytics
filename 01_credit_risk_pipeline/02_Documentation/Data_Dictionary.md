# Data Dictionary

This document defines the key features used in the **Default Risk Model** (Stage 2).

| Feature | Description | Type |
| :--- | :--- | :--- |
| `target_default` | Binary Target: 1 for Default (Charged Off), 0 for Fully Paid. | Integer |
| `loan_amnt` | The listed amount of the loan applied for by the borrower. | Numeric |
| `int_rate` | Interest rate on the loan. | Numeric |
| `dti` | Debt-to-Income ratio: A ratio calculated using the borrower’s total monthly debt payments divided by monthly gross income. | Numeric |
| `fico_avg` | The average of the borrower's high and low FICO score at the time of application. | Numeric |
| `term_months` | The number of payments on the loan (36 or 60 months). | Integer |
| `emp_length_years` | Employment length in years. | Numeric |
| `annual_inc` | The self-reported annual income provided by the borrower. | Numeric |
