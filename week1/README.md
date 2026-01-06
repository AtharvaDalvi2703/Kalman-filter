
---

## Contents Overview

### 1. Linear Regression (Theory + Implementation)
**Notebook:** `Linear_regression.ipynb`

This notebook covers:
- Mathematical formulation of multiple linear regression
- Derivation of the Ordinary Least Squares (OLS) estimator
- Conditions for invertibility of \( X^TX \) and effects of multicollinearity
- Residual analysis (homoscedasticity and normality checks)
- Influence diagnostics using leverage and Cook’s distance
- Comparison between manual NumPy implementation and `sklearn`’s `LinearRegression`

---

### 2. Salary Prediction & Bias Detection
**Notebook:** `Salary_dataset.ipynb`

This part focuses on responsible AI and fairness-aware modeling:
- Exploratory Data Analysis (EDA) of demographic and job-related features
- Handling missing values and outliers
- Encoding categorical variables with justification
- Training a baseline linear regression model
- Model evaluation using RMSE, MAE, and \( R^2 \)
- Fairness analysis with gender as a protected attribute, including:
  - Demographic Parity Difference
  - Equal Opportunity Difference
  - Disparate Impact Ratio
- Residual analysis and bias interpretation
- Model explainability using SHAP values

---

### 3. Deep Neural Network for Digit Classification
**Notebook:** `MNIST.ipynb`

This notebook implements a deep learning classifier using PyTorch:
- Custom neural network architecture for handwritten digit recognition
- Training loop using backpropagation and Adam optimizer
- Explanation of ReLU activation and PyTorch’s autograd system
- Evaluation on validation data



