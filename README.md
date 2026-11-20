# Session 2 Practice 2: CI/CD with GitHub Actions and Release

This repository demonstrates a CI/CD pipeline built with GitHub Actions.
Whenever `training_data.csv` changes on the `main` branch, the workflow:

1. Trains a linear regression model (`train_model.py`).
2. Pushes the resulting `linear_model.txt` to the `release` branch.
3. Creates a new GitHub release with the model file attached.

## Repository structure

| Path | Purpose |
| --- | --- |
| `.github/workflows/ci-cd.yml` | CI/CD workflow definition |
| `training_data.csv` | Training dataset (YearsExperience, Salary) |
| `train_model.py` | Trains the linear model and writes coefficients to `linear_model.txt` |
| `requirements.txt` | Python dependencies (`pandas`, `scikit-learn`, `joblib`) |

## Pipeline trigger

The workflow runs on every `push` and `pull_request` targeting `main`.
It only retrains and releases a model when `training_data.csv` is modified.
