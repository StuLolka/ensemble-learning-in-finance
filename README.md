[🇷🇺 Russian](README_RU.md)

# Ensemble Learning in Finance


📘 **Project Overview**

This repository contains a **course project** focused on applying **ensemble machine learning methods** (Bagging, Boosting, and Stacking) for the **analysis and prediction of stock returns**.  
The project is part of the *Applied Informatics* undergraduate program and is currently **in active development**.

---

## 🎯 **Objective**

The main goal of this research is to explore how ensemble models — such as **Random Forest**, **XGBoost**, and **Stacking Regressor** — can be used to **predict the next-day opening price** of a stock based on historical trading data.

---

## ⚙️ **Technologies Used**
- Python (pandas, numpy, matplotlib, seaborn)
- scikit-learn
- XGBoost
- Jupyter Notebook

---

## 🧩 **Methods Overview**

1. **Bagging (Bootstrap Aggregating)**  
   Multiple independent models are trained in parallel on bootstrapped subsets of data, and their predictions are aggregated (averaged or voted).  
   Example: *Random Forest*.

2. **Boosting**  
   Models are trained sequentially, with each new model focusing on correcting the mistakes of the previous ones.  
   Example: *XGBoost*.

3. **Voting**
   A parallel ensemble method that combines predictions of several independently trained models on the same dataset.
   In regression tasks, the final prediction is typically the average of base model outputs.
4. **Blending**
   A simplified version of stacking, where a meta-model is trained on predictions made by base models on a hold-out part of the training data.
   Blending is computationally efficient and easy to implement, but its performance depends strongly on how the hold-out set is chosen.

---

## 📈 **Current Results**

| Model | MAE ↓ | R² ↑ |
|:-------|:------:|:----:|
| RandomForestRegressor | 2.93 | 0.642 |
| XGBRegressor | 3.16 | 0.608 |
| Voting | 3.02 | 0.626 |
| Blending | 3.05 | 0.625 |

> Even without hyperparameter tuning, ensemble models demonstrate solid predictive performance and robustness to data noise.

---

## 🧮 **Data and Approach**

The dataset contains daily stock trading data, including open, close, high, low prices, and trading volume.  
The target variable is the **next-day opening price** (`tomorrow_open`), derived from the shifted `open` column.  
Train/test splits are made chronologically (no data leakage).  

Each model is evaluated using:
- **Mean Absolute Error (MAE)**
- **Coefficient of Determination (R² score)**

---

## 🚧 **Project Status**

⚠️ This project is **a work in progress**.  
Planned updates include:
- Feature engineering and lag-based features;
- Hyperparameter optimization (GridSearchCV / Optuna);
- Advanced visualization of prediction errors;
- Comparison with neural network models (LSTM, MLP).
