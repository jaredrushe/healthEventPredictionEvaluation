# Adverse Event Prediction — Model Evaluation

Evaluating machine learning models for predicting adverse health events in a remote patient monitoring setting, with an emphasis on rigorous evaluation design, distribution shift analysis, and real-world deployment considerations.

## Overview

Remote health monitoring platforms continuously collect wearable sensor data, contextual information, and derived behavioural indicators from patients. The goal of this project is to predict whether an **adverse health event** will occur within the next 24 hours — enabling clinicians to decide whether early intervention is needed.

This project goes beyond model building to focus on the often-overlooked question: **how should we evaluate models destined for high-stakes clinical use?**

## Key Focus Areas

- **Evaluation design** — choosing metrics and validation strategies that reflect real-world clinical utility, not just headline accuracy
- **Data integrity** — identifying and handling temporal leakage, post-outcome features, and concept drift in longitudinal patient data
- **Distribution shift** — analysing how model performance degrades when adverse event prevalence changes after deployment
- **Baseline rigour** — establishing meaningful baselines before introducing learned models
- **Adversarial evaluation** — stress-testing models and metrics to understand where they break down

## Project Structure

```
├── data/                   # Dataset
├── notebooks/              # Exploratory analysis and modelling
├── report/                 # Final technical report (PDF)
└── README.md
```

## Dataset

The dataset contains timestamped, repeated risk predictions per patient with a binary target variable:

| Label | Meaning |
|-------|---------|
| `y = 1` | Adverse health event within 24 hours |
| `y = 0` | No adverse event |

Features include a mixture of stable physiological signals, operational features, and intentionally problematic features requiring careful handling.

## Evaluation Approach

- Multiple metrics reported (beyond accuracy): precision, recall, F1, ROC-AUC, precision-recall AUC, PPV/NPV
- Patient-aware data splitting to prevent leakage across train/test sets
- Analysis of metric behaviour under a **5× prevalence drop** simulating post-deployment drift
- Uncertainty estimation via cross-validation variability and confidence intervals

## Tools & Libraries

- Python, scikit-learn, pandas, NumPy
- Matplotlib / Seaborn for visualisation
- Jupyter notebooks for analysis

## License

MIT
