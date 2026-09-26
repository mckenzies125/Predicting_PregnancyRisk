# Pregnancy Risk Classification

This project develops and evaluates statistical and machine learning models for classifying maternal health risk into **low-, mid-, and high-risk categories** using clinical measurements. The analysis compares several classification approaches and uses cross-validation, hyperparameter tuning, and model diagnostics to identify a model that balances predictive performance and interpretability.

## Project Overview

The goal of this project was to investigate whether routinely collected maternal health characteristics could be used to classify pregnancy risk. The analysis evaluates increasingly flexible classification methods, beginning with logistic regression and progressing to decision trees and ensemble methods.

The final model was a tuned Gradient Boosting classifier evaluated using 10-fold cross-validation.

## Methods

The modeling workflow included:

- Data preprocessing and preparation for multiclass classification
- Train/test splitting for model development and evaluation
- Logistic regression as an initial benchmark
- PCA and L1/L2 regularization to evaluate alternative model specifications
- Decision tree classification
- Bagging and ensemble methods
- Gradient Boosting classification
- Hyperparameter tuning for tree depth, learning rate, and number of estimators
- 10-fold cross-validation
- Evaluation using accuracy, precision, recall, F1 score, confusion matrices, and feature importance

## Results

The benchmark logistic regression model achieved approximately **65.0% test accuracy**, while a tuned decision tree improved test accuracy to approximately **82.3%**.

The final Gradient Boosting model achieved the following mean performance across 10-fold cross-validation:

| Metric | Mean |
| --- | ---: |
| Accuracy | 85.6% |
| Precision | 85.8% |
| Recall | 86.5% |
| F1 Score | 85.9% |

Cross-validation accuracy had a standard deviation of approximately **3.3 percentage points**, with fold-specific accuracies ranging from approximately **81.4% to 90.1%**.

## Feature Importance

Decision-tree feature importance analysis identified **blood sugar** as the strongest predictor of pregnancy risk, accounting for approximately **42.2%** of total feature importance.

The remaining feature importances were:

| Feature | Importance |
| --- | ---: |
| Blood Sugar | 42.2% |
| Systolic Blood Pressure | 19.4% |
| Age | 12.1% |
| Heart Rate | 10.9% |
| Body Temperature | 7.8% |
| Diastolic Blood Pressure | 7.6% |

These results suggest that blood sugar provided particularly strong discriminatory information for distinguishing maternal risk categories within this dataset.

## Model Evaluation

The final Gradient Boosting model was evaluated using multiple performance measures rather than accuracy alone. In addition to cross-validation, a confusion matrix was used to examine errors across the three risk categories.

Class-specific recall on the held-out test set was approximately:

- **Low risk:** 78.8%
- **Mid risk:** 86.8%
- **High risk:** 85.1%

This analysis helped assess not only overall predictive performance but also how effectively the model identified patients across different risk levels.

## Tools

- Python
- pandas
- NumPy
- scikit-learn
- Matplotlib
- Seaborn

## Repository Contents

- `Skrastins_MATH_457_Project.ipynb` — complete data analysis and modeling workflow
- `Skrastins_457FinalReport.pdf` — written project report
- `README.md` — project overview and results

## Key Takeaways

This project demonstrates an end-to-end multiclass classification workflow, including model comparison, hyperparameter tuning, cross-validation, performance evaluation, and interpretation of feature importance. Moving from a logistic regression benchmark to tree-based ensemble methods improved predictive performance, with the final Gradient Boosting model achieving approximately **85.6% mean accuracy across 10-fold cross-validation**.

## Context

This project was completed as the final project for **Introduction to Statistical Learning (MATH 457)**.
