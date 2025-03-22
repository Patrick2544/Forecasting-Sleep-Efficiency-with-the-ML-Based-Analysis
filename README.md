# 💤 Forecasting Sleep Efficiency using Machine Learning

**COMP 542 Project**  
A machine learning-driven analysis of behavioral, physiological, and lifestyle factors to predict sleep efficiency.

---

## 🧑‍🤝‍🧑 Team Members

- Brandon Ismalej  
- Jittapatana (Patrick) Prayoonpruk  
- John Lee  

---

## 🧠 Project Overview

Sleep efficiency is a vital indicator of sleep quality and overall health. This project utilizes advanced machine learning algorithms to forecast sleep efficiency using behavioral and lifestyle-related data. It aims to assist individuals and healthcare professionals in identifying patterns that influence sleep and promote better sleep hygiene.

---

## 📦 Dataset

- **Source:** [Kaggle - Sleep Efficiency Dataset](https://www.kaggle.com/)  
- **Samples:** 452 observations  
- **Features:** 14  
  - Sleep duration, REM %, deep/light sleep %, caffeine/alcohol consumption, smoking, gender, awakenings, etc.  
- **Target:** Sleep Efficiency (continuous)  
- **Train-Test Split:** 80% train / 20% test  
- **Cross Validation:** k-fold with k=5  

---

## 🧹 Data Preprocessing

- **Categorical Encoding:** Binary encoding for gender and smoking status  
- **Missing Values:** Imputed using mean/median values within groups  
- **Feature Selection Techniques:**
  - Correlation Analysis
  - Mutual Information
  - Recursive Feature Elimination (RFE)
  - Random Forest Importance

---

## 🎯 Selected Key Features

| Feature              | Correlation | Impact Description                               |
|----------------------|-------------|--------------------------------------------------|
| Light Sleep %        | -0.82       | Strong negative impact on sleep efficiency       |
| Deep Sleep %         | +0.79       | Strong positive correlation (most restorative)   |
| Awakenings           | -0.55       | More awakenings reduce sleep quality             |
| Smoking Status       | -0.29       | Behavioral factor negatively affecting sleep     |

---

## 🔍 Models Used

### 1. Multiple Linear Regression (with stepAIC)
- **Why:** Simplicity, interpretability, and effectiveness for linear patterns  
- **Metric:** Adjusted R², AIC, BIC  
- **RMSE:** 0.0617

### 2. XGBoost (Gradient Boosting)
- **Untuned RMSE:** 0.0563  
- **Tuned RMSE:** **0.0494** (best performing model)

### 3. LightGBM
- **All Features RMSE:** 0.0511  
- **After Feature Selection RMSE:** 0.0525

### 4. Random Forest
- **All Features RMSE:** 0.0503  
- **With Feature Selection RMSE:** 0.0557

---

## 🧪 Model Evaluation

| Model                   | RMSE    | Notes                                |
|------------------------|---------|--------------------------------------|
| Multiple Regression     | 0.0617  | Stepwise selected features           |
| XGBoost (untuned)       | 0.0563  | Baseline GBM                         |
| XGBoost (tuned)         | **0.0494**  | ⭐️ Best performance               |
| LightGBM (all features) | 0.0511  | Fast and efficient                   |
| Random Forest           | 0.0503  | Robust ensemble model                |

---

## 📈 Tools & Libraries

- Python: `scikit-learn`, `xgboost`, `lightgbm`, `pandas`, `matplotlib`
- R: `stepAIC`, `ggplot2`, `lm()`, diagnostic plotting
- Jupyter & RMarkdown for exploratory and final analysis

---

## 🚀 Potential Applications

- Personalized sleep tracking and health monitoring
- Integration into smartwatches, fitness trackers, or health apps
- Use in sleep disorder clinics for patient screening

---

## 🧩 Future Enhancements

- Deploy models in a web/mobile interface
- Integrate additional physiological signals (heart rate, HRV)
- Use time-series modeling for longitudinal sleep data

---
