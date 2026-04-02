# 🔥 Hacker News Post Popularity Prediction

> Predicting whether a Hacker News post will go viral using supervised machine learning on self-collected web data.

![Python](https://img.shields.io/badge/Python-3.12-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange)
![License](https://img.shields.io/badge/License-MIT-green)
![NYCU](https://img.shields.io/badge/NYCU-AI%20Capstone%202026-red)

---

## 📌 Research Question

> **Can we predict whether a Hacker News post will become popular (score ≥ 10) based solely on its title text and posting time?**

Understanding what makes online content succeed has implications for content strategy, community moderation, and social media research.

---

## 📊 Dataset

| Property | Value |
|---|---|
| Total Stories | 799 |
| Popular (score ≥ 10) | 367 (45.9%) |
| Not Popular (score < 10) | 432 (54.1%) |
| Features | 19 engineered features |
| Collection Date | April 1, 2026 |
| Source | Hacker News Firebase API |

### Features
- **Temporal:** hour, dayofweek, is_weekend
- **Linguistic:** title_length, title_wordcount, has_question, has_number
- **Keywords:** has_ai, has_gpt, has_llm, has_python, has_github, has_google, etc.

### Label
A post is labeled **popular (1)** if its score is ≥ 10, otherwise **not popular (0)**.

---

## 🤖 Models

| Model | Accuracy | F1-Score | AUROC |
|---|---|---|---|
| Logistic Regression | 0.652 | 0.466 | 0.638 |
| **Random Forest** | **0.859** | **0.846** | **0.901** |

All results from **5-fold stratified cross-validation**.

---

## 🧪 Experiments

| # | Experiment | Key Finding |
|---|---|---|
| 1 | Training Data Size | RF improves with more data; LR stays flat at ~65% |
| 2 | Class Balancing (SMOTE) | Minimal effect — dataset already near-balanced |
| 3 | Feature Importance | `dayofweek` and `hour` account for 60% of RF decisions |
| 4 | PCA Dimensionality Reduction | 2 PCA components beat all 19 features for LR |
| 5 | Hyperparameter Sensitivity | RF plateaus at n=100 trees |

---

## 📁 Repository Structure
```
├── hacker_news_dataset.csv        # Main dataset (799 rows, 28 columns)
├── AI_HW1_314540056.pdf           # Full project report
├── confusion_matrices.png         # Training-set confusion matrices
├── cv_confusion_matrices.png      # Cross-validated confusion matrices
├── exp1_learning_curve.png        # Experiment 1: Learning curves
├── exp3_feature_importance.png    # Experiment 3: Feature importance
├── exp4_pca.png                   # Experiment 4: PCA results
├── exp5_hyperparameter.png        # Experiment 5: Hyperparameter sensitivity
└── README.md
```

---

## 🔑 Key Findings

- ⏰ **Timing beats content** — when you post matters far more than what keywords you use
- 🌲 **Random Forest (85.9% CV accuracy)** massively outperforms Logistic Regression (65.2%)
- 📉 **PCA helps linear models** — 2 components beat 19 raw features for Logistic Regression
- 🔄 **SMOTE had minimal effect** — the near-balanced dataset didn't need oversampling

---

## 🛠️ How to Reproduce
```bash
# Install dependencies
pip install requests pandas scikit-learn imbalanced-learn matplotlib seaborn

# Run data collection
python collect_data.py

# Run experiments
python train_models.py
```

---

## 📚 References

1. Pedregosa et al., *Scikit-learn: Machine Learning in Python*, JMLR 2011
2. Lemaitre et al., *Imbalanced-learn*, JMLR 2017
3. Hacker News Firebase API — https://hacker-news.firebaseio.com/v0/
4. Chawla et al., *SMOTE*, JAIR 2002

---

## 👤 Author

**Student ID:** 314540056  
**Course:** Undergraduate AI Capstone — NYCU Spring 2026  
**Project:** #1 — Dataset Construction and Analysis
