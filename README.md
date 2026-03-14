# 🩺 Diabetes Risk Prediction Model

![Python](https://img.shields.io/badge/Python-3.10+-blue) ![XGBoost](https://img.shields.io/badge/XGBoost-Enabled-red) ![Accuracy](https://img.shields.io/badge/Accuracy-96%25-brightgreen) ![AUC](https://img.shields.io/badge/AUC-0.97-green) ![License](https://img.shields.io/badge/License-MIT-yellow)

### XGBoost Classifier | 96,146 Records | SMOTE Balancing | 96% Accuracy

A machine learning model that predicts diabetes risk using clinical data. Built with XGBoost and SMOTE oversampling to handle class imbalance, achieving **96% accuracy** and **0.97 AUC score**.

---

## 📊 Model Performance

| Metric | Score |
|---|---|
| Accuracy | 96% |
| AUC-ROC | 0.97 |
| Precision (Diabetic) | 0.83 |
| Recall (Diabetic) | 0.73 |
| F1-Score (Diabetic) | 0.78 |

---

## ✨ Key Features

- **XGBoost Classifier:** 100 estimators, learning rate 0.05, max depth 6 — optimized for tabular clinical data.
- **SMOTE Oversampling:** Handles severe class imbalance (91% non-diabetic vs 9% diabetic) by synthetically balancing training data.
- **Threshold Optimization:** Default threshold adjusted from 0.5 to 0.42 for better diabetic recall in clinical screening context.
- **Feature Scaling:** StandardScaler applied for consistent model performance.
- **Model Persistence:** Saved via `joblib` for production deployment.

---

## 🔍 Top Predictive Features

1. **blood_glucose_level** — Strongest predictor (correlation: 0.42)
2. **HbA1c_level** — Second strongest (correlation: 0.41)
3. **age** — Moderate predictor (correlation: 0.26)
4. **bmi** — Body mass index (correlation: 0.21)
5. **hypertension** — Comorbidity factor (correlation: 0.20)

---

## 🛠️ Tech Stack

| Component | Tool |
|---|---|
| Language | Python 3.10+ |
| ML Framework | XGBoost, Scikit-Learn |
| Imbalance Handling | SMOTE (imbalanced-learn) |
| Data Processing | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Model Export | Joblib |

---

## 📁 Dataset

- **Source:** Diabetes Prediction Dataset
- **Records:** 96,146 (after removing 3,854 duplicates)
- **Features:** 8 clinical attributes
- **Target:** Binary (0 = Non-Diabetic, 1 = Diabetic)
- **Class Distribution:** 91% Non-Diabetic, 9% Diabetic

---

## 🚀 Quick Start

**1. Clone the repo:**
```bash
git clone https://github.com/YasraNafees/diabetes-risk-prediction.git
cd diabetes-risk-prediction
```

**2. Install dependencies:**
```bash
pip install -r requirements.txt
```

**3. Run the notebook:**
```bash
jupyter notebook diabetes_prediction.ipynb
```

**4. Load saved model:**
```python
import joblib
import pandas as pd

model = joblib.load('diabetes_risk_model.pkl')

new_data = pd.DataFrame({
    'gender': [1],
    'age': [45],
    'hypertension': [0],
    'heart_disease': [1],
    'smoking_history': [2],
    'bmi': [28.5],
    'HbA1c_level': [6.2],
    'blood_glucose_level': [140]
})

prediction = model.predict(new_data)
print("Diabetes Prediction:", prediction[0])
```

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first.
