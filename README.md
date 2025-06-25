# Higgs AMS-Aware Classifier

A deep learning model for Higgs boson signal classification, trained using a physics-inspired AMS-aware loss function.

This project builds on the work of [Baldi et al. (2014)](https://www.nature.com/articles/ncomms5308) by introducing a custom loss function that directly optimizes the Approximate Median Significance (AMS), a key metric for discovery in high-energy physics.

---

## Project Goals

- Train a baseline neural network which utilizes standard binary cross-entropy loss
- Train a neural network which utilizes AMS-aware loss with a differentiable approximation of the actual metric
- Compare AMS-aware training vs. standard binary cross-entropy
- Provide a fully pipeline for training, validating, and testing physics informed models

---

## Dataset

This project uses the **Kaggle Higgs Boson ML Challenge** dataset:
- `training.csv`: 250,000 labeled events with weights
- `test.csv`: 550,000 unlabeled events, no weights (used to evaluate model AMS scores through Kaggle)

Download it from [Kaggle](https://www.kaggle.com/competitions/higgs-boson/data).

---

## Pre-processing

For the most part the datasets were clean to work with since they were synthesized (based on CERN's ATLAS experiment).
Steps taken for pre-processing:
- Mean imputation for missing values (normally distributed data, means introduced no skewness)
- Feature columns identified as beginning with 'DER_' or 'PRI_' (all feature cols began with either one of these prefixes)
- Target columns identified as 'Weight' and 'Label' ('Weight' gives the significance of the event, and 'Label' is string values of either 's' or 'b', indicating signal or background event occurence)
