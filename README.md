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

## 🧠 Ensemble Methods Used

This project explores several ensemble learning approaches aimed at improving predictive accuracy and model robustness.  

1. **Bagging (Bootstrap Aggregating)**  
   Multiple independent models are trained in parallel on different bootstrapped subsets of the original dataset,  
   and their predictions are then averaged (or aggregated via voting).  
   This approach reduces variance and helps prevent overfitting.  
   **Example:** *Random Forest*.

2. **Boosting**  
   Models are trained **sequentially**, where each new model focuses on correcting the errors made by the previous ones.  
   Boosting often achieves high predictive accuracy but requires more training time and can be less interpretable.  
   **Example:** *XGBoost*.

3. **Voting**  
   A **parallel** ensemble method where several models, trained on the same data, make predictions,  
   and the final output is calculated as the **average** of their predictions (for regression tasks).  
   This method helps stabilize results and reduce variance, especially when combining models of different types that complement each other.

4. **Blending**  
   A simplified version of stacking, where the meta-model is trained not on cross-validation predictions,  
   but on a **hold-out** portion of the training data.  
   Blending is simpler and faster to implement, but its performance heavily depends on how the hold-out sample is selected.  
   When data is limited, it tends to be less statistically stable than full stacking.


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
