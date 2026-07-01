# FITE Classification MLOps

This repository contains the final reproducible notebook for the FITE Classification Challenge.

## Leakage Policy

- `train_data.csv` is used for EDA, preprocessing decisions, validation, model selection, and final training.
- `test_data.csv` is used only once after model selection to generate the final Kaggle submission.
- No information from the Kaggle test set or public leaderboard is used for tuning, feature engineering, or model selection.

## MLflow

MLflow was used to track experiments. Each run logs model parameters, holdout F1-macro, weighted F1, accuracy, and classification report artifacts.

The best model selected by holdout validation was:

- Bagging (OOB Eval)
- Holdout F1-macro: 0.995385

## DVC Data Versioning

The raw CSV files are tracked with DVC and are not stored directly in GitHub.

To reproduce the data locally after cloning the repository:

```bash
pip install dvc dvc-gdrive
dvc pull

This downloads the dataset from the configured Google Drive DVC remote using the .dvc tracking file.
