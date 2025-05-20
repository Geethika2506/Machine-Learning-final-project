# Machine-Learning-final-project
# Credit Card Fraud Detection

# Overview
This project tackles the problem of **credit card fraud detection** using machine learning techniques. Fraud detection is crucial in real-world financial systems, where even a small percentage of undetected fraud can result in significant financial loss.

We experimented with multiple models, preprocessing techniques, and evaluation metrics to develop a robust fraud detection system, focusing particularly on improving recall for the minority class (fraudulent transactions).

---

# Team Members:
- Tianyang Chen  
- Geethika Reddy Konda  
- Nicolás Leyva González  
- Kareem Rami Jamil Hawwash  
- Omar Mekkawi Yassin  

---

# Data Source:
- Dataset: [Kaggle Credit Card Fraud Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/data)  
- Size: 284,807 transactions  
- Features: 30 numerical features + 1 target (`Class`)

---

# Problem Characteristics
- Highly **imbalanced** dataset (only ~0.17% fraud cases).
- Features V1 to V28 are anonymized PCA components.
- `Time`, `Amount`, and `Class` are the only original features.

---

 # Preprocessing Steps
1. **Exploratory Data Analysis (EDA)** – Class distribution, amount trends, and time-based behavior.
2. **Feature Engineering** – Created `Hour` and `TimeBin` from `Time`, log-transformed `Amount`.
3. **One-Hot Encoding** – Applied to categorical features (`TimeBin`).
4. **Resampling Strategy** – Used **SMOTE** + **RandomUnderSampler** to handle class imbalance.
5. **Scaling** – Standardized `Amount` and `Hour`.

---

# Models Tested
- Baselines: Dummy Classifier, Logistic Regression  
- Classical ML:  
  - Random Forest (with and without tuning)  
  - Decision Tree  
  - Support Vector Machine (SVM)  
- Advanced:  
  - XGBoost  
  - Multilayer Perceptron (MLP)

---

# Model Performance Summary

| Model             | Recall | F1-Score | AUC-ROC |
|------------------|--------|----------|---------|
| Dummy Classifier | 0.00   | 0.00     | 0.50    |
| Logistic Reg.     | 0.88   | 0.12     | 0.97    |
| Random Forest     | 0.85   | 0.63     | 0.98    |
| XGBoost           | 0.84   | 0.50     | 0.98    |
| SVM (Linear)      | 0.86   | 0.12     | 0.97    |
| MLP               | 0.86   | 0.32     | 0.98    |
| Random Forest (Tuned) | 0.85 | 0.63   | 0.98    |

> **Final Choice**: **Random Forest** (tuned with BayesSearchCV) due to its strong recall, good precision, and lowest false positives.

---

 # Evaluation Strategy
- Metrics used:
  - **Recall**: Prioritized to catch most fraudulent transactions.
  - **AUC-ROC**: Assesses model's ability to distinguish between classes.
  - **F1-Score**: Balances precision and recall.
- Confusion matrices and performance graphs supported model selection.

---

# Team Collaboration
- Work was divided into:
  - Data Cleaning and EDA
  - Model Design and Evaluation
  - Report Writing and Visualization
- Regular check-ins and GitHub collaboration ensured smooth progress.

---

# Repository
GitHub Link: [`Geethika2506/Machine-Learning-final-project`](https://github.com/Geethika2506/Machine-Learning-final-project)

---

# Future Work
- Deploying the model into a real-time fraud detection system.
- Exploring ensemble learning and time-series models.
- Integrating user behavior and geographic data.

---

 # Date
April 28, 2025
