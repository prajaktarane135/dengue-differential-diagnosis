# dengue-differential-diagnosis
Borderline-SMOTE and explainable stacked machine-learning pipeline for dengue differential diagnosis
# Explainable Stacked Machine Learning for Dengue Differential Diagnosis

This repository contains the complete analytical pipeline accompanying
the study:

**Explainable Stacked Machine Learning for Differentiating Dengue from
Community-Acquired Bacterial Infection Using Haematological Markers**

## Classification task

The implemented task is binary differential diagnosis:

- Dengue: class 1
- Confirmed or suspected/probable community-acquired bacterial
  infection: class 0

Dengue severity was not modelled.

## Methods included

- Data cleaning and temporal-feature construction
- Median imputation
- Feature standardization
- Borderline-SMOTE
- Random Forest
- XGBoost
- Logistic Regression
- Stacking ensemble
- Confusion matrices and performance metrics
- ROC and precision-recall analysis
- Bootstrap confidence intervals
- Calibration assessment
- Negative predictive value
- Explicit analytical representation of the fitted meta-classifier
- SHAP and LIME explanations of the XGBoost base learner

## Dataset

The analysis uses the publicly available longitudinal dataset reported
by Yasuda et al.

Original study DOI:
https://doi.org/10.1371/journal.pone.0258936

Figshare dataset:
https://figshare.com/articles/dataset/Unique_characteristics_of_new_complete_blood_count_parameters_the_Immature_Platelet_Fraction_and_the_Immature_Platelet_Fraction_Count_in_dengue_patients/16810771?file=31085452 

Download `figsharecsv.csv` from Figshare and upload it to the Google
Colab session before executing the notebook. The notebook expects the
file at:

`/content/figsharecsv.csv`

The dataset is not redistributed through this repository.

## Execution

1. Open the notebook in Google Colab.
2. Upload `figsharecsv.csv` to the Colab `/content/` directory.
3. Run all cells sequentially from the beginning.
4. Do not execute cells out of order.

The analysis uses `random_state=42`.

## Validation limitation

The implementation uses an observation-level 80:20 train-test split.
Because the dataset contains repeated longitudinal observations, records
from the same participant may occur in both partitions. Patient-grouped
and external validation were not performed.

## Interpretability limitation

SHAP and LIME explain the fitted XGBoost base learner. They do not
explain the complete stacking ensemble. The analytical equation
represents the fitted Logistic Regression meta-classifier and does not
constitute independent model validation.

## Licence

Add the applicable software licence and follow the terms specified for
the original dataset.
