## Technical Summary – Chronic Kidney Disease (CKD) Prediction

### Objective
To develop a machine learning-based risk stratification tool for detecting Chronic Kidney Disease using structured clinical data. The model should maximize recall to minimize false negatives, ensuring patients at risk are not missed.

---

### Data Preparation
- **Dataset:** UCI Chronic Kidney Disease dataset (400 records, binary classification)
- **Features Used:** 18 numerical and categorical lab/clinical variables (e.g., hemoglobin, creatinine, albumin, hypertension)
- **Preprocessing Steps:**
  - Renamed features for clarity
  - Imputed missing numerical values with median and categorical values with mode
  - Binary encoded categorical features
  - Applied `StandardScaler` for numeric features
  - Addressed class imbalance with SMOTE

---

### Modeling Workflow
- **Train/Test Split:** 80/20 stratified split
- **Baseline Model:** Logistic Regression (for benchmarking)
- **Advanced Models:**
  - Random Forest Classifier (with GridSearchCV)
  - XGBoost Classifier (with GridSearchCV)

**Hyperparameter Tuning:**
- Performed using `GridSearchCV` with 5-fold `StratifiedKFold` cross-validation
- Evaluation metric: ROC AUC

---

### Model Evaluation
| Model                  | Accuracy | Recall | Precision | F1-Score | ROC AUC |
|------------------------|----------|--------|-----------|----------|---------|
| Logistic Regression    | 0.93     | 0.96   | 0.91      | 0.93     | 0.97    |
| Random Forest (tuned) | 0.96     | 0.98   | 0.94      | 0.96     | 0.98    |
| XGBoost (tuned)       | **0.975** | **0.99** | **0.96**   | **0.98**   | **0.99**   |

**Selected Model:** XGBoost (tuned) — best combination of recall and ROC AUC.

---

### Feature Importance & Interpretability
- **Top Predictors:**
  - Hemoglobin (inverse relationship)
  - Serum Creatinine
  - Albumin
  - Diabetes Mellitus
  - Hypertension

---

### Conclusion
The tuned XGBoost classifier provides excellent recall and AUC, crucial for clinical scenarios where minimizing false negatives is vital. The model is production-ready for integration into a broader patient risk monitoring system.

---

### Next Steps
- Model Deployment: FastAPI + Docker + AWS EC2
- Extend evaluation with external validation dataset
- Add monitoring for concept drift and retraining pipeline
- Collaborate with clinicians to set risk thresholds for alerting

---

Prepared by: [Ruban Sellathurai]
Date: [July 6th, 2025]

