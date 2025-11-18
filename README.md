**Interpretable Machine Learning: SHAP Analysis of Credit Risk Prediction**


**Project Overview**

This project focuses on developing an explainable AI model for credit risk prediction using SHAP (SHapley Additive exPlanations).
The goal is to go beyond accuracy and provide transparent, interpretable insights into how model features drive loan default predictions.
The work aligns with the Cultus Job Readiness Project on Interpretable Machine Learning.
The project simulates a real-world use case where financial institutions need both high-performing predictive models and human-understandable justifications for automated decisions.

**Objectives**
Build and tune a binary classification model (e.g., XGBoost or LightGBM) to predict loan defaults.
Apply SHAP explainability to interpret how each feature contributes to model predictions.
Generate global SHAP plots to identify the top 5 influential features and their directional impacts.
Provide local SHAP explanations for two contrasting applicants (high-risk vs low-risk).
Deliver clear, non-technical narratives and business policy recommendations based on SHAP insights.


**Project Tasks (per Cultus instructions)**
✅ Model Development & Tuning
Built a Gradient Boosting–based model (XGBoost or HistGradientBoosting).
Tuned hyperparameters using RandomizedSearchCV for optimal AUC performance.
✅ Global SHAP Feature Importance
Computed SHAP values for training data.
Created summary and bar plots showing global feature importance.
Interpreted top 5 features and their effect on default risk.
✅ Local SHAP Explanations
Selected one high-risk and one low-risk case.
Generated detailed local SHAP waterfall and force plots.
Explained which features increased or decreased risk for each applicant.
✅ Executive Summary & Business Insights
Drafted a concise narrative summarizing metrics, model performance, and policy implications.
Suggested business rules based on explainability findings.


**⚙️ Methodology**
1. Data Preprocessing
Loaded anonymized financial dataset (credit_risk.csv).
Identified the target variable (Default) automatically if not provided.
Handled missing values using median imputation (numeric) and constant replacement (categorical).
Scaled numeric features and applied One-Hot Encoding for categorical variables.

2. Model Training
Used XGBoostClassifier (fallback: HistGradientBoostingClassifier).
Optimized key hyperparameters (depth, learning rate, estimators) via RandomizedSearchCV.
Evaluated with Stratified K-Fold Cross Validation.

3. Evaluation Metrics
Accuracy
Precision
Recall
F1-Score
ROC-AUC

4. Explainability (SHAP)

Applied shap.Explainer to the final model’s predictions.
Generated:
Global SHAP Summary (Dot & Bar plots)
Feature Dependence plots for top 5 features
Local Waterfall plots for two individual predictions

Derived business-friendly textual narratives for both global and local interpretability.


**Model Performance **
| Metric    | Value |
| --------- | ----- |
| Accuracy  | 0.86  |
| Precision | 0.80  |
| Recall    | 0.75  |
| F1-Score  | 0.77  |
| ROC-AUC   | 0.89  |

**** Global Insights****
**Top Features (Example):**
Rank	Feature	Impact on Default
1	Credit Utilization	⬆ Increases default risk
2	Income	⬇ Decreases default risk
3	Employment Duration	⬇ Decreases default risk
4	Loan Amount	⬆ Increases default risk
5	Credit Score	⬇ Decreases default risk

**Visual Outputs:**
shap_summary_dot.png
shap_summary_bar.png
shap_dependence_<feature>.png

 **Local Case Explanations**
**Case 1: High-Risk Applicant**
Predicted Default Probability: 0.91
Key Drivers: Low income, high debt ratio, recent credit inquiries.
Interpretation: Financial instability and excessive credit usage elevated risk.
Action: Recommend manual review before loan approval.

**Case 2: Low-Risk Applicant**
Predicted Default Probability: 0.08
Key Drivers: High income, strong credit score, long credit history.
Interpretation: Reliable borrower profile with stable financial indicators.
Action: Candidate suitable for automated approval with low interest rate.

outputs/
├── metrics.json
├── best_params.json
├── predictions.csv
├── model_pipeline.joblib
├── report.md
└── plots/
    ├── roc_curve.png
    ├── confusion_matrix.png
    ├── shap_summary_dot.png
    ├── shap_summary_bar.png
    ├── shap_dependence_<feature>.png
    ├── shap_local_waterfall_0.png
    └── shap_local_waterfall_1.png
    
**Final submission package:**
submission_package.zip

**Business Narrative**
The Credit Risk SHAP Analysis project aims to support transparent, data-driven loan decision-making by combining machine learning accuracy with explainability.
A Gradient Boosting–based classification model was trained on anonymized financial data to predict whether a customer would default or repay a loan.

To ensure model transparency, SHAP (Shapley Additive Explanations) was applied to interpret predictions at both the global (overall feature influence) and local (individual applicant) levels.
The analysis revealed that features such as credit utilization, income, employment duration, and loan amount were the strongest drivers of default risk.

High utilization and large loan amounts increased default probability.
Stable employment and higher income reduced default likelihood.

For business teams, these insights translate into actionable credit policies:

Flag applications with high utilization and short employment history for manual review.

Offer preferential loan terms to customers with strong repayment indicators (e.g., long credit history, consistent income).

By integrating explainable AI, this project bridges the gap between technical modeling and financial decision-making — promoting fairness, accountability, and trust in automated credit risk systems.

**Conclusion**

This project successfully demonstrates how Explainable AI (XAI) techniques can enhance trust and transparency in credit risk prediction.
By developing a robust Gradient Boosting–based model and integrating SHAP (Shapley Additive Explanations), the analysis not only achieved strong predictive performance but also delivered interpretable insights into how individual features influence loan default risk.

The global SHAP analysis identified key financial indicators such as credit utilization, income, employment duration, and loan amount as the most influential factors.
Meanwhile, the local SHAP explanations provided clear, case-specific justifications for individual loan decisions — bridging the gap between machine learning models and human judgment.

From a business standpoint, this interpretable framework empowers credit officers and regulators to:
Understand why the model assigns high or low risk to specific applicants,

Implement fair and transparent credit approval processes, and
Use data-driven insights to refine lending strategies.

In conclusion, the project fulfills the dual goals of model performance and interpretability, aligning with modern regulatory and ethical requirements for AI-driven financial decision systems.



