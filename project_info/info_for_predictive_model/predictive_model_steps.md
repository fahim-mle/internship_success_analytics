# Predictive Modelling Workflow: Student At-Risk Classification

This document outlines a **step-by-step guide** for building a predictive model to classify students as "at risk" (high or medium) by Week 5, using structured data with a majority of categorical variables.

---

## 1. **Objective Definition**

- Clearly define the classification task: Predict whether a student is at high or medium risk based on Week 5 data.
- The target variable is `risk` with two possible outcomes: `high` or `medium`.

---

## 2. **Data Overview**

- Dataset contains 41 predictor variables and 1 target variable.
- The majority of predictor variables are categorical (e.g., origin country, academic status, student cohort, subjects, etc.).

---

## 3. **Data Preprocessing**

- Convert the `risk` variable to binary (e.g., `0 = medium`, `1 = high`).
- Review and clean the data:
  - Handle missing values.
  - Ensure all variables are in the expected format.
  - Drop any identifier or non-predictive fields.

---

## 4. **Feature Transformation**

- Apply numeric weight mappings for categorical features using the predefined `feature_mappings.json`.
- For each categorical column:
  - Map the category to a numeric weight.
  - Replace or supplement original values with these numeric scores.
- Example columns to convert: `country`, `course`, `student_cohort`, `academic_status`, `subject_1` through `subject_3`, etc.

---

## 5. **Feature Selection (Optional)**

- Use top N features based on correlation or domain importance.
- Consider dimensionality reduction if overfitting is a concern.

---

## 6. **Dataset Splitting**

- Split the data into training and testing sets.
- Use stratification to maintain class balance.
- Suggested split: 80% train, 20% test.

---

## 7. **Model Training**

- Use a suitable classifier (e.g., Random Forest, XGBoost, Logistic Regression).
- Enable class weighting or use sampling techniques if the dataset is imbalanced.

---

## 8. **Model Evaluation**

- Evaluate using the following metrics:
  - Accuracy
  - Precision/Recall
  - F1-Score
  - ROC AUC Score
- Use a confusion matrix to visualize performance.

---

## 9. **Feature Importance Analysis**

- For tree-based models, extract and visualize the top features contributing to the prediction.
- Optional: Use SHAP or permutation importance for deeper insights.

---

## 10. **Model Persistence**

- Save the trained model to disk for later inference.
- Save preprocessing steps (encoders, imputers) if reusability is required.

---

## 11. **Deployment/Use** (Optional)

- Deploy in a Streamlit app, command-line tool, or web API for internal use.
- Add input validation and real-time predictions for new student records.
