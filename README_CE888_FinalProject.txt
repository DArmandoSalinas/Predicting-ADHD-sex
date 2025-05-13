
CE888 Final Project – ADHD & Sex Prediction
Student: Diego Armando Salinas Lugo
Student ID: ds24353 / 2401168

--------------------------------------------------

Project Description

This project was developed in response to an NHS request to build a data-driven decision-support system to:

1. Assist with ADHD diagnosis using socio-demographic, emotional, parenting, and fMRI data.
2. Predict a participant's sex, with a specific concern for avoiding underdiagnosis in female ADHD cases.
3. Ensure that the system is fair, explainable, and aligned with GDPR and clinical safety standards.

The project is divided into two stages:
- Stage 1 focuses on data cleaning, feature engineering, and preparing training/validation datasets.
- Stage 2 focuses on training and tuning machine learning models, evaluating their fairness, and interpreting results using explainability tools.

--------------------------------------------------

How to Run the Code

1. Download the official dataset provided via Moodle and place it in the same directory as the notebooks.
2. Open and run all cells in the notebook:
   - Exploration.ipynb
     Loads raw data, handles missing values, performs stratified splitting,
     merges all features and saves:
       - cleaned_train_data.csv
       - cleaned_validation_data.csv
3. Then open and run:
   - Modelling_Stage2.ipynb
     Loads the cleaned datasets, splits the validation set into new validation + final test sets,
     trains, tunes, and evaluates models for ADHD and Sex classification,
     uses LIME and SHAP for explainability, and performs fairness evaluation.

--------------------------------------------------

Assumptions Made

- Stratification for data splits was done using a custom combined_label (ADHD_Outcome + Sex_F).
- Iterative Imputer was used for numerical missing values, as recommended.
- Missing ethnicity values were replaced with 3 ("Unknown").
- Feature selection was based on mutual information scores.
- Dimensionality reduction on fMRI data used KernelPCA with RBF kernel, keeping 100 components.
- ADHD and Sex were treated as independent binary classification problems.
- Final model evaluation was performed only once using a hold-out test set.
- Evaluation focused on recall and fairness, especially for female ADHD cases.
- Models were selected based on performance, fairness, and interpretability.

--------------------------------------------------

Files Included

- Exploration.ipynb – Stage 1 notebook
- Modelling_Stage2.ipynb – Stage 2 notebook
- cleaned_train_data.csv / cleaned_validation_data.csv (generated)
- README.txt – This document

--------------------------------------------------

Final Model Choices

Task                  | Final Model         | Justification
---------------------|---------------------|-----------------------------------------------------------
ADHD Diagnosis        | Random Forest       | High recall, strong generalization, fair subgroup results.
Sex Classification    | Logistic Regression | Best female recall, balanced fairness, interpretable.

--------------------------------------------------

Contact

University email: ds24353@essex.ac.uk

Project completed as part of CE888 – MSc Data Science and its Applications – University of Essex
