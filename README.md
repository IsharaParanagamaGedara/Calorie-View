# 🔥 Calorie View | EDA 📊 | CatBoost 😸

A machine learning pipeline that predicts **calories burned** during physical activity using physiological and demographic features.  
Built using **CatBoost**, **feature interaction engineering**, and **log-transformed regression**, this project was developed for the **Kaggle Playground Series – Season 5, Episode 5 (2025)**.

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)
![Model](https://img.shields.io/badge/Model-CatBoost-lightblue?logo=catboost)
![RMSLE](https://img.shields.io/badge/Eval-RMSLE-critical)
[![View on Kaggle](https://img.shields.io/badge/Kaggle-View%20Notebook-blue?logo=kaggle)]([https://www.kaggle.com/code/YOUR_USERNAME/calorie-view-catboost](https://www.kaggle.com/code/sulaniishara/calorie-view-eda-catboost))

---

## 📂 Dataset Overview

This project combines **three aligned datasets** to model and predict caloric expenditure during physical activity.

### 📘 Datasets Used:

| Dataset          | Records    | Description                                                                 |
|------------------|------------|-----------------------------------------------------------------------------|
| `train.csv`      | 750,000    | Core training data with full feature and target availability                |
| `test.csv`       | 250,000    | Same structure as train, but missing the target (`Calories`)                |
| `calories.csv`   | 15,000     | Benchmark/reference dataset from a prior Kaggle competition                 |

Each row includes:

- **Demographics**: `Sex`, `Age`, `Height`, `Weight`
- **Activity stats**: `Duration`, `Heart_Rate`, `Body_Temp`
- **Target**: `Calories` burned 🔥

---

## 🎯 Project Objective

The main goal is to build a **high-performance regression model** that accurately estimates **calories burned** based on workout and demographic features.

### ✅ Highlights of the Approach

- 📊 **EDA & Distributions**: Examined calorie ranges, demographics, and correlations  
- 🧩 **Feature Cross Terms**: Created all pairwise feature interactions for numeric variables  
- 🧠 **Modeling with CatBoost**: A GPU-efficient gradient boosting framework ideal for mixed data  
- 📈 **Log-Target Transformation**: Applied `log1p` to stabilize calorie variance  
- 🔎 **Model Evaluation**: Used **5-fold cross-validation** and the **RMSLE** metric  
- 📤 **Final Submission**: Predicted values clipped to the range `[1, 314]` and exported

---

## 💡 Feature Engineering

Cross-term interaction features between all 6 numerical inputs:

```python
["Age", "Height", "Weight", "Duration", "Heart_Rate", "Body_Temp"]
````

Generated 15 new features like `Age_x_Weight`, `Duration_x_Heart_Rate`, etc.
This enhanced the model’s ability to capture latent relationships in physical dynamics.

---

## 📊 Visualizations Included

* 🔹 **Feature Importance** from CatBoost (gain-based)
* 🔹 **Actual vs Predicted (OOF)** scatter plot
* 🔹 **KDE curves** comparing actual vs predicted calorie distributions

All charts styled with the **PuOr** color palette and light grid overlays.

---

## 🧠 Tech Stack

* Python 3.10+ 🐍
* Libraries: `catboost`, `optuna`, `pandas`, `seaborn`, `matplotlib`, `sklearn`
* Environment: Kaggle Notebook / JupyterLab

---

## ✅ Final Results

* 🧪 **Mean RMSLE**: `~0.0601 ± 0.0002`
* ⏱️ **Avg. Train Time per Fold**: `~202s`
* 📁 **Submission File**: `submission.csv`

---

## 📜 License

This project is licensed under the MIT License.
All datasets are publicly available through Kaggle and credited to their original authors.

---

## 🤝 Acknowledgements

* 🔷 [Kaggle Playground Series – Season 5]([https://www.kaggle.com/competitions/playground-series-s5e5](https://www.kaggle.com/competitions/playground-series-s5e5/overview))
* 🔷 [Calories Burnt Prediction Dataset]([https://www.kaggle.com/datasets/ruchikakumbhar/calories-burnt-prediction](https://www.kaggle.com/datasets/ruchikakumbhar/calories-burnt-prediction))

---

> 🔥 *Predict your burn. Fuel your performance.*


