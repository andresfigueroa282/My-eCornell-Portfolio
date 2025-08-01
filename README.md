# 📘 Lab 8: Define and Solve a Machine Learning Problem

## 🔍 Overview
In this project, I implemented the full machine learning lifecycle to predict the **“Life Ladder”** score (a measure of subjective well-being) using the **World Happiness Report (WHR) 2018** dataset. The objective was to build a regression model that estimates national happiness based on socioeconomic, health, and governance-related features.

---

## 🗂️ Dataset

- **Source:** `WHR2018Chapter2OnlineData.csv`
- **Rows:** 1,562
- **Features:** 19
- **Target Variable:** `Life Ladder` (numeric happiness score)

---

## 🔧 Problem Formulation

- **Type:** Supervised Learning  
- **Task:** Regression  
- **Label:** Life Ladder (continuous value)  
- **Features Selected (after EDA):**
  - Log GDP per capita
  - Social support
  - Healthy life expectancy at birth
  - Freedom to make life choices
  - Perceptions of corruption
  - Positive affect
  - Negative affect
  - Democratic Quality
  - Delivery Quality

---

## 📊 Exploratory Data Analysis (EDA)

- Addressed missing values using **mean imputation**
- Evaluated feature correlation with the target (`Life Ladder`)
- Dropped features with low correlation or risk of **data leakage**
- Assessed **outliers** using boxplots (retained them to reflect global variability)
- Visualized target distribution and feature relationships

---

## 🛠️ Data Preparation

- Feature selection based on correlation and domain relevance
- One-hot encoding skipped due to dropping the `country` column
- Applied **StandardScaler** to normalize feature distribution
- Split data: 80% training, 20% testing

---

## 🤖 Modeling

### ✅ Model 1: Linear Regression
- **R² Score:** 0.774  
- **RMSE:** 0.541  
- **MAE:** 0.420  

### ✅ Model 2: Random Forest Regressor
- **R² Score:** 0.899  
- **RMSE:** 0.362  
- **MAE:** 0.283  
- → **Best performing model**

### ✅ Model 3: Gradient Boosting Regressor
- **R² Score:** 0.858  
- **RMSE:** 0.429  
- **MAE:** 0.339  

---

## 🧪 Evaluation Metrics

| Metric | Interpretation |
|--------|----------------|
| R²     | % of variance explained by the model |
| RMSE   | Average prediction error range |
| MAE    | Average absolute difference between actual and predicted |

---

## 🌲 Feature Importance (Random Forest)

| Feature                          | Importance |
|----------------------------------|------------|
| Log GDP per capita               | 0.395      |
| Healthy life expectancy          | 0.312      |
| Positive affect                  | 0.091      |
| Social support                   | 0.070      |

---

## 🛠️ Optimization Attempt

- **GridSearchCV** used for Random Forest hyperparameter tuning  
- Best Parameters:  
  `n_estimators=100`, `max_depth=20`, `min_samples_split=2`, `min_samples_leaf=1`
- **Outcome:** Original model performed slightly better than the optimized version

---

## 🚀 Final Takeaways

- **Random Forest** was the most effective model with ~90% R².
- Model insights revealed key contributors to national well-being: **GDP**, **health**, and **emotions**.
- Future work would involve better feature engineering, hyperparameter optimization, and addressing outliers.

---

## 🧠 Skills & Tools Used

- **Languages & Libraries:** Python, Pandas, NumPy, Seaborn, Matplotlib, scikit-learn
- **ML Concepts:** Supervised Learning, Regression, Model Evaluation, Hyperparameter Tuning
- **Models Used:** Linear Regression, Random Forest Regressor, Gradient Boosting Regressor
- **Techniques:** 
  - Exploratory Data Analysis (EDA)
  - Feature Selection & Engineering
  - Data Cleaning & Preprocessing
  - Standardization (StandardScaler)
  - Model Training & Validation
  - Evaluation Metrics: R², RMSE, MAE
  - Feature Importance Analysis
  - Grid Search (GridSearchCV)
- **Visualization Tools:** Seaborn, Matplotlib
- **Other Skills:** End-to-End ML Lifecycle, Data-Driven Decision Making, Interpreting Socioeconomic Indicators
