[🇷🇺 Russian](README_RU.md)

# Ensemble Methods for Predicting Stock Return and Price Direction

This repository contains the code and materials for a research project dedicated to applying ensemble machine learning methods to predict stock returns and the direction of price movement based on historical data.

The project is implemented in a Jupyter Notebook and is accompanied by a written report that includes data analysis, model descriptions, and interpretation of the results.

---

## 📌 Project Goals

- Evaluate the applicability of ensemble models to the task of predicting stock returns.
- Compare the performance of several algorithms:
  - RandomForest  
  - ExtraTrees  
  - XGBoost  
  - LightGBM  
  - HistGradientBoosting  
  - Ridge Regression  
  - KNN
- Assess ensemble architectures: VotingRegressor, weighted voting, and blending.
- Measure prediction accuracy for both **return magnitude** and **price direction**.
- Analyze the robustness of models across hundreds of individual time series.
- Examine the impact of hyperparameter tuning and weight assignment within the ensemble.
- Measure the computational performance of all algorithms.

---

## 📊 Metrics

Two key metrics are used in the project:

- **SMAPE (Symmetric Mean Absolute Percentage Error)** — measures the relative prediction error.
- **Direction Accuracy** — the proportion of correctly predicted price movement directions (up/down).

Taken together, these metrics reflect both numerical precision and practical predictive usefulness.

---

## 🧠 Models Used

- RandomForestRegressor  
- ExtraTreesRegressor  
- XGBoostRegressor  
- LightGBMRegressor  
- HistGradientBoostingRegressor  
- Ridge Regression (within a Pipeline)
- KNeighborsRegressor (within a Pipeline)

Each model also has a tuned version with optimized hyperparameters.

---

## 🧩 Ensemble Strategies

The following ensemble techniques were evaluated:

### 1. VotingRegressor (equal weights)
All models contribute equally to the final prediction.

### 2. VotingRegressor (weighted)
Stronger models receive higher weights; weaker ones receive minimal influence.

### 3. Ensemble of Strongest Models
A combination of RandomForest, ExtraTrees, and XGBoost (both with and without custom weights).

### 4. Blending
Predictions of base models are combined using a Ridge meta-model.

---

## 📊 Model Performance

Average performance of the tuned models and the final ensemble:

| Model                                  | SMAPE ↓      | Direction Accuracy ↑ | Runtime          | <55% assets | >95% assets |
|----------------------------------------|--------------|-----------------------|------------------|-------------|-------------|
| **XGBoostRegressor**           | 104.2157     | 0.7423                | 01:57            | 37          | 7           |
| **LightGBMRegressor**          | 107.6480     | 0.7206                | 00:32            | 48          | 3           |
| **HistGradientBoostingRegressor**      | 101.6070     | 0.7412                | 01:54            | 45          | 4           |
| **RandomForestRegressor**      | 97.5782      | 0.7523                | 08:47            | 29          | 5           |
| **ExtraTreesRegressor**        | 98.4191      | 0.7486                | 03:04            | 31          | 5           |
| **KNeighborsRegressor**        | 138.0007     | 0.6329                | 00:29            | 102         | 4           |
| **Final ensemble**    | **97.5133**  | **0.7531**            | **14:30**        | **28**      | **5**       |

---
