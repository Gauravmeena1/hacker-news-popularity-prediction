# Hacker News Post Popularity Prediction
**NYCU AI Capstone — Project #1 | Spring 2026**

## Research Question
Can we predict whether a Hacker News post will become popular 
(score ≥ 10) based on title features and posting time?

## Dataset
- **Size:** 799 stories
- **Source:** Hacker News Firebase API
- **Collected:** April 1, 2026
- **Task:** Binary Classification (Popular vs Not Popular)

## Files
| File | Description |
|------|-------------|
| `hacker_news_dataset.csv` | Main dataset (799 rows, 28 columns) |
| `AI_HW1_Report.pdf` | Full project report |
| `confusion_matrices.png` | Model confusion matrices |
| `exp1_learning_curve.png` | Learning curve experiment |
| `exp3_feature_importance.png` | Feature importance plot |
| `exp4_pca.png` | PCA experiment results |

## Features
- **Temporal:** hour, dayofweek, is_weekend
- **Linguistic:** title_length, title_wordcount, has_question, has_number
- **Keywords:** has_ai, has_gpt, has_python, has_github, etc.

## Models Used
- Logistic Regression (scikit-learn)
- Random Forest (scikit-learn)

## Results
| Model | Accuracy | F1 | AUROC |
|-------|----------|----|-------|
| Logistic Regression | 0.652 | 0.466 | 0.638 |
| Random Forest | 0.859 | 0.846 | 0.901 |
```
