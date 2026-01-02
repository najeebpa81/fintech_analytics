# Visual Insights

This folder contains key visualizations from the credit risk pipeline — designed for presentations, reports, and quick client understanding.

All plots are high-resolution PNGs for easy sharing.

## Files & Explanations

### `roc_curve_default_model.png`
- **What it shows**: Receiver Operating Characteristic (ROC) curve for the Default Risk Model on unseen test data
- **Key metric**: AUC-ROC = **0.7042**
- **Client takeaway**: 
  - The model has good ability to separate safe loans from risky ones (AUC > 0.7 is solid for credit risk).
  - Higher AUC means better overall ranking of risk — even if not perfect.

### `precision_recall_curve_default_model.png`
- **What it shows**: Precision-Recall trade-off when predicting defaults
- **Key metric**: Average Precision (AP) = **0.369**
- **Client takeaway**:
  - Focuses on performance for the minority class (defaults ~20%)
  - At practical thresholds, the model catches ~60–70% of actual defaults with reasonable precision.
  - Important for imbalanced data like lending.

### `shap_summary_bar_default_model.png`
- **What it shows**: Top features ranked by global impact on default predictions
- **Top drivers**: Grade, interest rate, term length, DTI, FICO
- **Client takeaway**:
  - The model relies on intuitive, fair risk factors — no surprises or hidden biases.
  - Explains overall model behavior across all loans.

### `shap_summary_beeswarm_default_model.png`
- **What it shows**: Direction and distribution of feature impact
- **Color**: Red = high value, Blue = low value
- **Client takeaway**:
  - High interest rates, worse grades, longer terms → strongly increase default risk (red dots on right)
  - High FICO, high income → strongly decrease risk (red dots on left)
  - Visual proof the model learned logical patterns.

### `shap_force_plot_high_risk.png`
- **What it shows**: Local explanation for a **high-risk** prediction (predicted 93.9% default probability — actual default)
- **Client takeaway**:
  - Every decision is explainable: "This loan was flagged due to G grade, 30.89% rate, 60-month term, high DTI, renting"
  - Perfect for customer communication or regulatory justification.

### `shap_force_plot_low_risk.png`
- **What it shows**: Local explanation for a **low-risk** prediction (predicted 0.6% default — fully paid)
- **Client takeaway**:
  - Shows protective factors: A grade, low rate, high FICO/income, home ownership
  - Builds trust: "This loan was approved because of strong credit profile"

### `threshold_analysis_line_chart.png`
- **What it shows**: Business impact of different risk thresholds
- **Client takeaway**:
  - Clear trade-off: stricter threshold → fewer defaults but lower volume
  - Recommended balance at ~0.45: ~55% approval, ~11.4% default rate among approved, captures ~69% of defaults
  - Enables data-driven policy decisions

These visualizations make the models **transparent, trustworthy, and actionable** — turning complex ML into clear business insights.
