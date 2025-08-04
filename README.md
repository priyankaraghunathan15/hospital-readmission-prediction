# 🏥 Hospital Readmission Risk Prediction

This project aims to predict hospital readmission in diabetic patients using structured clinical data. Leveraging machine learning models like Logistic Regression, Random Forest, and XGBoost, the goal is to identify patients at risk of being readmitted within 30 days after discharge — a key challenge in improving care quality and reducing healthcare costs.

<p align="center">
  <img src="images/hosptial-readmission-rate.png" alt="Hospital Risk Predictor Image" width="650"/>
</p>
---

## 📊 Dataset Overview

- **Source**: UCI Machine Learning Repository  
- **Records**: Over 100,000 anonymized inpatient visits  
- **Target Variable**: Readmission status (`<30 days`, `>30 days`, or `No`)  
- **Task**: Binary classification — `Readmitted` (within 30 days) vs `Not Readmitted`

---

## 🔄 Workflow Summary

1. **Data Cleaning**
   - Dropped patient identifiers
   - Handled missing and placeholder values
   - Encoded categorical variables

2. **EDA**
   - Analyzed age, diagnoses, length of stay, admission types
   - Identified strong class imbalance in target variable

3. **Preprocessing**
   - Applied SMOTE to balance classes
   - Feature selection to remove redundancy

4. **Model Training**
   - Built and tuned Logistic Regression, Decision Tree, Random Forest, and XGBoost
   - Used stratified 10-fold cross-validation
   - Evaluated with Accuracy, Precision, Recall, and AUC

---

## 📈 Model Performance

| Model              | Accuracy | AUC   |
|-------------------|----------|-------|
| Logistic Regression | ~0.89    | ~0.58 |
| Decision Tree       | ~0.90    | ~0.59 |
| Random Forest       | ~0.93    | ~0.60 |
| XGBoost             | **~0.94**| **~0.61** |

> ⚠️ Due to class imbalance, accuracy is inflated — AUC gives a more balanced view.

---

## 📁 Project Structure

```text
.
├── Hospital Readmission Risk Prediction.ipynb   # Main notebook
├── data/
│   ├── 01_raw_patient_records.csv
│   ├── 02_cleaned_data_initial.csv
│   ├── 03_cleaned_data_final.csv
│   ├── 04_balanced_data_smote.csv
│   └── 05_selected_features.csv
├── images/
│   └── hospital-readmission-rate.png
├── requirements.txt
├── README.md
└── .gitignore
```

---

## 📌 Key Insights

- **Top Predictors**: Number of inpatient stays, number of diagnoses, and length of hospitalization
- **SMOTE** improved recall for minority class but requires careful cross-validation to avoid overfitting
- **XGBoost** provided the best performance while maintaining interpretability

---

## 🧠 Conclusion

This project demonstrates the value of machine learning in predicting 30-day hospital readmissions among diabetic patients. While the models achieved high accuracy, moderate AUC scores suggest room for improvement. Future work could include:

- Time-series modeling of patient visit history
- Inclusion of unstructured data (e.g., discharge summaries)
- Use of interpretability tools like SHAP for clinical decision support

By identifying at-risk patients early, this work supports efforts to reduce readmissions and enhance care quality in healthcare systems.

