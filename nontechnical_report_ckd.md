## Chronic Kidney Disease (CKD) Prediction

**Author:** Ruban Sellathurai

---

### Executive Summary

**Project Overview and Goals:**
This project aims to build a reliable machine learning model to predict Chronic Kidney Disease (CKD) based on patient lab results and clinical indicators. The goal is to identify high-risk individuals early using a combination of classical ML models, hyperparameter tuning. The models are trained on a curated clinical dataset with structured, anonymized features. Key challenges addressed include class imbalance and missing values common in clinical datasets.

---

### Findings

The best-performing model for CKD prediction is the **XGBoost Classifier**, achieving:
- **Accuracy:** 0.975
- **Recall (CKD - Class 1):** 0.99
- **Precision (Class 0):** 0.96
- **F1-Score:** 0.98
- **ROC AUC Score:** 0.99

This was followed by the tuned **Random Forest** model and a **baseline Logistic Regression** model. The XGBoost model demonstrated superior recall and AUC, making it an excellent choice for clinical screening tools where false negatives must be minimized.

---

### Results and Interpretation

#### Global Feature Importance
- **High Impact Features:** Hemoglobin (inverse), Serum Creatinine, Albumin, Diabetes Mellitus, Hypertension
- **Moderate Impact:** Packed Cell Volume, Blood Urea, Appetite, Anemia, Pedal Edema

These align with clinical literature on CKD pathophysiology. Visualizations were used to compare the ROC curves across models.

---

### Future Research and Development

**Technical Improvements:**
- Integrate feature selection with recursive elimination
- Use ensemble stacking (LogReg + XGB + RF) to further boost performance
- Perform external validation using public UCI or hospital datasets

**Productization:**
- Convert the model into a REST API
- Deploy on a cloud platform like AWS EC2 with Docker and enable continuous model monitoring

**Clinical Relevance:**
- Collaborate with domain experts to validate thresholds
- Integrate with EHR systems for passive patient monitoring

---

### Rationale
Chronic Kidney Disease is a progressive condition that can lead to kidney failure if not detected early. According to the CDC, approximately 15% of U.S. adults have CKD. Early intervention can significantly slow disease progression. This project provides a data-driven risk stratification approach to aid clinicians in identifying high-risk patients.

---

### Research Question
Can we build a high-recall predictive model to identify patients at risk of CKD using routine lab values and clinical observations?

---

### Dataset
- **Source:** UCI ML Repository, cleaned and restructured.
- **Records:** 400 patients
- **Target:** CKD (binary: 0 = Not CKD, 1 = CKD)
- **Features:** Age, Blood Pressure, Hemoglobin, Creatinine, Sodium, Potassium, etc.

Missing values were imputed using median/mode strategies. Categorical features were binary-encoded. SMOTE was used to balance the training data.

---

### Methodology
- **EDA:** Identified missing data patterns and feature distributions
- **Preprocessing:** Normalized numerical columns, one-hot encoded categoricals
- **Train/Test Split:** Stratified 80/20
- **Baseline Model:** Logistic Regression
- **Advanced Models:** Random Forest, XGBoost
- **Hyperparameter Tuning:** GridSearchCV with StratifiedKFold
- **Evaluation:** Accuracy, ROC AUC, Precision/Recall

---

### Visual Summary
**ROC Curve:**
- All tuned models achieved AUC ~0.99

---

### Notebook
- [`module-24-final-analysis.ipynb`](module-24-final-analysis.ipynb)
- [Exploratory data analysis](https://github.com/RSellathurai/BH_AI_ML_CapstoneProject/blob/main/kidney_disease_eda.ipynb)
- [Exploratory data analysis Summary](https://github.com/RSellathurai/BH_AI_ML_CapstoneProject/blob/main/README.md)

---

### Contact
**Your Name**
Email: ruban.sellathurai@gmail.com
LinkedIn: [https://www.linkedin.com/in/rubansellathurai/](https://www.linkedin.com/in/rubansellathurai/)
GitHub: [https://github.com/RSellathurai](https://github.com/RSellathurai)

