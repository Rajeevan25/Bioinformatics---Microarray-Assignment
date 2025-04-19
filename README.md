# Gene Expression Analysis in AML and ALL Type Leukemia

## Overview

This project analyzes gene expression data to distinguish between two types of Leukemia: Acute Myeloid Leukemia (AML) and Acute Lymphoblastic Leukemia (ALL). The dataset includes normalized expression levels for over 7,000 genes across labeled training and testing sets.

## Dataset

- **Format**: Gene expression levels (already normalized)
- **Labels**: AML or ALL
- **Split**: Separate training and test sets provided

---

## Questions Addressed

### Q1: Build a Classification Model

We developed interpretable models to classify samples as AML or ALL based on gene expression:

- **Models Used**:
  - **Logistic Regression**: Offers transparency via coefficients
  - **Decision Tree Classifier**: Visual representation of decision logic
  - **Random Forest Classifier**: Used with SHAP explainability
  - **XGBoost**: Applied SHAP for feature interpretation

- **Evaluation**:
  - Accuracy was calculated on the test set
  - Confusion matrices plotted for each classifier
  - Hyperparameter tuning was done on training data only

### Q2: Identify Important Genes

- **Feature Importance Extraction**:
  - Logistic regression coefficients (absolute magnitude)
  - Decision tree feature importances
  - SHAP (SHapley Additive exPlanations) for tree-based models

- **Insights**:
  - Identified key genes that consistently contributed to distinguishing between AML and ALL
  - Visualized using SHAP summary plots

### Q3: Unsupervised Clustering

- **Techniques Used**:
  - **KMeans**
  - **Agglomerative Clustering**
  - **Spectral Clustering**

- **Evaluation**:
  - Calculated **Purity** using the known labels
  - Reported the best purity score across methods
  - **PCA** was used to examine data variance and determine dimensionality for visualization

- **Purpose**:
  - Demonstrated that clustering methods can reveal underlying structure in gene expression data even without supervision
  - Useful in exploratory phases, especially when labels are unavailable

---

## Files Included

- `classifier_models.py`: Contains code for training Logistic Regression, Decision Tree, Random Forest, XGBoost models
- `explainability.py`: SHAP analysis and feature importance plots
- `clustering_analysis.py`: Code for KMeans, Agglomerative, and Spectral Clustering with purity score calculation
- `pca_plot.py`: PCA analysis and explained variance plot
- `AML_ALL_data/`: Folder containing training and test data files

---

## Requirements

- Python 3.7+
- Required libraries:
  - `scikit-learn`
  - `xgboost`
  - `shap`
  - `matplotlib`
  - `seaborn`
  - `pandas`
  - `numpy`

Install dependencies using:

```bash
pip install -r requirements.txt
