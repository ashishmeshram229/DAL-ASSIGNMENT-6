# DA5401 Assignment 6: Imputation via Regression for Missing Data

**Student Name:** Ashish Meshram  
**Roll Number:** DA25M016  
**Course:** DA5401 – Data Analytics Laboratory  
**Assignment:** 6  

---

## Overview
This assignment explores **handling missing data** in the UCI Credit Card Default Clients Dataset using multiple imputation strategies.  
The goal is to understand how missing data techniques affect the performance of a **Logistic Regression classifier** for predicting credit defaults.

---

## Dataset
- **Source:** [UCI Credit Card Default Clients Dataset - Kaggle](https://www.kaggle.com/datasets/uciml/default-of-credit-card-clients-dataset)  
- **Target Variable:** `default payment next month`  
- **Missing Data Simulation:** MAR (5–10% missing in `AGE` and `BILL_AMT` columns)

---

## Imputation Strategies
| Dataset | Method | Description |
|---------|--------|-------------|
| **A** | Median Imputation | Simple baseline, robust to outliers |
| **B** | Linear Regression | Predicts missing values using linear correlations |
| **C** | KNN Regression | Captures non-linear relationships and local patterns |
| **D** | Listwise Deletion | Removes all rows with missing data |

---

## Model Training
- **Classifier:** Logistic Regression  
- **Preprocessing:** StandardScaler to normalize features  
- **Data Split:** 80% train / 20% test (stratified by target variable)

---

## Performance Summary

| Model | Accuracy | Precision (Macro) | Recall (Macro) | F1-Score (Macro) | Weighted F1 |
|-------|----------|------------------|----------------|-----------------|-------------|
| A     | 0.81     | 0.75             | 0.61           | 0.63            | 0.77        |
| B     | 0.81     | 0.75             | 0.61           | 0.63            | 0.77        |
| C     | 0.81     | 0.75             | 0.61           | 0.62            | 0.77        |
| D     | 0.81     | 0.76             | 0.59           | 0.61            | 0.76        |

**Key Insights:**  
- Median imputation is a strong baseline.  
- Linear regression preserves feature correlations.  
- KNN regression captures complex, non-linear patterns, especially for minority classes.  
- Listwise deletion reduces dataset size, lowering recall and potentially introducing bias.

---

## Recommendations
- **Preferred:** KNN Regression (non-linear) for realistic credit risk modeling.  
- **Alternative:** Linear Regression Imputation when simplicity and interpretability are prioritized.  
- **Avoid:** Listwise deletion unless missingness is completely random (MCAR).  

> Treating missing data intelligently improves model fairness, accuracy, and decision-making reliability.

---

## Tools & Libraries
- **Python 3.9+**  
- **Libraries:** `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`  
- **Environment:** Jupyter Notebook  

---

## Author
**Ashish Meshram**  
**Roll Number:** [Your Roll Number Here]  
