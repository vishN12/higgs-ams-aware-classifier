# Higgs AMS-Aware Classifier

A deep learning model for Higgs boson signal classification, trained using a physics-inspired AMS-aware loss function.

This project builds on the work of [Baldi et al. (2014)](https://www.nature.com/articles/ncomms5308) by introducing a custom loss function that directly optimizes the Approximate Median Significance (AMS), a key metric for discovery in high-energy physics.

---

## Project Goals

- Reproduce baseline models: shallow NN, deep NN, XGBoost
- Implement and evaluate a custom **AMS-aware loss function**
- Compare AMS-aware training vs. standard binary cross-entropy
- Provide a fully reproducible pipeline for physics-informed ML

---

## Dataset

This project uses the **Kaggle Higgs Boson ML Challenge** dataset:
- `training.csv`: 250,000 labeled events with weights
- `test.csv`: unlabeled data (not used for evaluation here)

Download it from [Kaggle](https://www.kaggle.com/competitions/higgs-boson/data).

---
