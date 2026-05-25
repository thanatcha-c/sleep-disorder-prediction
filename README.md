# Sleep Disorder Prediction using Random Forest

## Overview
This project applies a Random Forest classifier to predict sleep disorder conditions (None, Insomnia, Sleep Apnea) based on health and lifestyle data from the Sleep Health and Lifestyle Dataset on Kaggle.

## Dataset
- **Source:** [Sleep Health and Lifestyle Dataset](https://www.kaggle.com/datasets/uom190346a/sleep-health-and-lifestyle-dataset) by Laksika Tharmalingam
- **Size:** 374 records, 13 features
- **Target:** Sleep Disorder (None / Insomnia / Sleep Apnea)

## Methodology
1. **Data Preprocessing** — removed irrelevant columns, split Blood Pressure into Systolic/Diastolic, filled missing values, applied Label Encoding to categorical features
2. **Train/Test Split** — 80:20 with Stratified Sampling to preserve class distribution
3. **Baseline Evaluation** — Stratified 10-Fold Cross Validation (mean accuracy: 88.30%)
4. **Hyperparameter Tuning** — GridSearchCV with 10-Fold CV
   - Best parameters: `n_estimators=50`, `max_depth=5`, `min_samples_leaf=1`
   - Best CV accuracy: 89.63%
5. **Final Evaluation** — tested on held-out test set


## Results
- **Test Accuracy: 96.00%**
- **Top features:** BMI Category, Occupation, Blood Pressure (Systolic/Diastolic)

## Libraries
```
pandas, numpy, scikit-learn, matplotlib, seaborn
```

## Limitations
- Small dataset (374 records) — may affect generalizability
- Class imbalance: None (59%) dominates over Insomnia and Sleep Apnea
