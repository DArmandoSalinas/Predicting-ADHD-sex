# ADHD & Sex Prediction — CE888 Final Project

[![Python 3.10+](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/downloads/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-classification-F7931E.svg)](https://scikit-learn.org/)
[![SHAP](https://img.shields.io/badge/SHAP-explainability-FF6B6B.svg)](https://shap.readthedocs.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

NHS-inspired decision-support research: predict **ADHD diagnosis** and **participant sex** from psychosocial and fMRI data with emphasis on **fairness**, **explainability**, and **female ADHD underdiagnosis**.

**Author:** Diego Armando Salinas Lugo · University of Essex (CE888)

📹 [Project walkthrough](https://youtu.be/F41ycarl3_U)

---

## Pipeline

| Stage | Notebook | Purpose |
|-------|----------|---------|
| 1 | `Exploration.ipynb` | Cleaning, feature engineering, train/val export |
| 2 | `Modelling_Stage2 - Final.ipynb` | Model tuning, fairness, SHAP & LIME |

## Quick start

1. Place the course dataset in the project root (provided via Moodle).
2. Run `Exploration.ipynb` → generates `cleaned_train_data.csv`, `cleaned_validation_data.csv`
3. Run `Modelling_Stage2 - Final.ipynb` → trains/evaluates final models

```bash
pip install pandas numpy scikit-learn shap lime matplotlib seaborn jupyter
jupyter notebook Exploration.ipynb
```

## Final models

| Task | Model | Rationale |
|------|-------|-----------|
| ADHD diagnosis | Random Forest | High recall, strong generalization |
| Sex classification | Logistic Regression | Best female recall, interpretable |

## Methodology

- Stratified splits with custom combined labels
- KernelPCA (RBF, 100 components) on fMRI features
- Mutual-information feature selection
- Fairness evaluation across subgroups
- LIME + SHAP for clinical interpretability

## Disclaimer

Academic research project. Not validated for clinical deployment without institutional governance review.

## License

MIT — see [LICENSE](LICENSE).
