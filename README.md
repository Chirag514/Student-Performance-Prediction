# 📊 Student Performance Prediction

This machine learning project aims to predict academic performance (grade classification) of students based on various factors like study time, absences, parental support, and extracurricular activities. By analyzing these elements, the model helps identify students who might need academic support and offers insights into improving educational outcomes.

---

## 🧠 Problem Statement

Traditional methods of assessing academic performance often overlook key non-academic factors. This project uses machine learning to build a predictive model based on:

- Study habits
- Attendance
- Parental involvement
- Extracurricular activities
- Behavioural patterns

---

## 🧹 Data Preprocessing

- ✅ No null values
- 📏 Applied standard scaling on numeric features
- 🔢 Numerical columns used: `['Age', 'ParentalEducation', 'StudyTimeWeekly', 'Absences', 'ParentalSupport', 'GPA']`
- ❌ Dropped irrelevant features: `['StudentID', 'Music', 'Sports', 'Volunteering']`

---

## 📈 Exploratory Data Analysis (EDA)

Key Findings:
- Strong correlation:
  - `GPA` and `GradeClass`: -0.78
  - `Absences` and `GradeClass`: 0.73
  - `GPA` and `Absences`: -0.92
- Weak or no correlation with `GradeClass`: `Gender`, `Age`, `Tutoring`, `Sports`, `Volunteering`
- Parental support correlates positively with higher GPA.

---

## 🔍 Feature Importance

Estimated using **Random Forest**:
- Most important: **GPA**
- Least important: **Tutoring**

---

## 🧲 Models Used

| Model                  | Accuracy     |
|------------------------|--------------|
| K-Nearest Neighbors    | 0.697        |
| Support Vector Machine | 0.816        |
| Logistic Regression    | 0.749        |
| Decision Tree          | 0.839        |
| **Random Forest**      | **0.923**    |
| Gradient Boosting      | 0.904        |
| AdaBoost               | 0.887        |
| Gaussian Naive Bayes   | 0.770        |
| **XGBoost**            | **0.906**    |

📌 **Best Models:** Random Forest & XGBoost  
📉 **Least Performing:** KNN & Logistic Regression

---

## 🧰 Model Evaluation

- ROC-AUC used for performance comparison
- Random Forest showed highest AUC, especially for Class 4
- Class 0 is consistently harder to classify

---

## 🛠️ Hyperparameter Tuning

- **Random Forest:** Tuned using `n_estimators`, `max_depth`, `min_samples_split`
- **XGBoost:** Tuned with `n_estimators`, `max_depth`, `learning_rate`, `gamma`
- Cross-validation improved model performance by 2-5%

---

## ✅ Conclusion

- Balanced dataset with no nulls
- Feature selection and scaling improved model accuracy
- GPA is the most influential factor
- Random Forest and XGBoost offer the highest accuracy (≈ 93%)
- Hyperparameter tuning and validation ensured robustness
