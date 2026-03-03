# 🚀 Fault Detection Using LightGBM  
### IEEE SB GEHU – ML Challenge Submission

This repository contains a high-performance machine learning solution developed for binary fault detection using structured sensor data.

---

# 📌 Problem Statement

The dataset consists of **47 numerical features (F01–F47)** collected from an embedded monitoring system.

The objective is to predict:

- `0` → Normal Operation  
- `1` → Faulty Condition  

The problem is framed as a **binary classification task** optimized for maximum accuracy.

---

# 📊 Dataset Summary

- Total Samples: **43,776**
- Features: **47 numerical variables**
- Target Variable: `Class`
- Class Distribution:
  - Normal: ~60%
  - Faulty: ~40%
- No missing values
- All features are continuous float values

---

# 🧠 Methodology

## 1️⃣ Exploratory Data Analysis (EDA)

- Verified class distribution
- Analyzed feature correlations
- Checked feature statistics
- Confirmed absence of missing values

---

## 2️⃣ Baseline Model

Model used:
- **LightGBM**
- Stratified 5-Fold Cross Validation
- Early stopping enabled
- Threshold optimization applied

Baseline CV Accuracy:

**98.96%**

---

## 3️⃣ Hyperparameter Optimization

- Used Optuna for tuning
- Optimized binary log-loss
- Compared against baseline

Result:
Minimal accuracy improvement → baseline was already strong.

---

## 4️⃣ Feature Importance-Based Selection (Major Improvement)

Instead of using all 47 features:

- Extracted feature importance from trained model
- Ranked features by contribution
- Tested multiple subsets (Top 30, 32, 35, 38)

Best performance achieved using:

🎯 **Top 35 Features**

Final Cross-Validation Accuracy:

**99.04%**

---

# ⚙️ Final Model Configuration

- Model: LightGBM
- n_estimators: 2000
- learning_rate: 0.03
- num_leaves: 64
- subsample: 0.8
- colsample_bytree: 0.8
- Cross-validation: Stratified 5-Fold
- Early stopping enabled
- Optimized decision threshold: **0.405**

---

# 📈 Model Performance

| Configuration | CV Accuracy |
|---------------|------------|
| All 47 Features | 98.96% |
| Top 35 Features | **99.04%** |

---

# 📂 Repository Contents

ML-Fault-Detection/
│
├── first_submission.ipynb # Complete training & experimentation
├── FINAL.csv # Final submission file
├── requirements.txt
└── README.md



---

# 🛠️ Installation

Clone the repository:

```
git clone https://github.com/mayankarora-cse23/IEEE_ML.git
cd first_submission
```

Install dependencies:

```
pip install -r requirements.txt
```

# 🚀 How to Run

Open the notebook:

- first_submission.ipynb

Run all cells to:

- Train LightGBM model

- Perform feature selection

- Generate FINAL.csv

# 🔍 Key Insights

- LightGBM outperformed XGBoost.

- Feature pruning improved generalization more than hyperparameter tuning.

- Threshold optimization significantly improved accuracy.

- Ensemble attempts did not outperform optimized single model.

- The dataset is highly separable, enabling near 99% accuracy.


# 👨‍💻 Author

- Mayank Arora and Priyanh Rathore
- IEEE ML Challenge Submission
- GitHub: https://github.com/mayankarora-cse23
