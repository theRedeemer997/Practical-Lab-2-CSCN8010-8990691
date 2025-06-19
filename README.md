# Practical Lab 2 - Diabetes Progression Prediction

## Overview

This project aims to predict diabetes disease progression one year after baseline using the **Scikit-Learn Diabetes dataset**. The task involves data exploration, cleaning, modeling with different machine learning algorithms, evaluation, and comparison of results.

---

## Contents

- Data Loading and Preparation
- Exploratory Data Analysis (EDA)
- Data Cleaning
- Feature Selection
- Model Training:
  - Polynomial Regression (Univariate and Multivariate)
  - Decision Trees
  - k-Nearest Neighbors (kNN)
- Model Evaluation
- Conclusion

---

## How to Run

1. Clone the repository:

   git clone https://github.com/theRedeemer997/Practical-Lab-2-CSCN8010-8990691.git

2. Create a virtual environment using

   ```bash
   python3 -m venv .venv

   ```

3. Activate the virtual environment using

   ```bash
       source ./.venv/Scripts/activate
   ```

4. Install dependencies using the following
   ```bash
   pip install -r requirements.txt
   ```

---

## Dataset

- **Source**: `sklearn.datasets.load_diabetes()`
- **Features**: 10 numeric variables including BMI, age, blood pressure, etc.
- **Target**: Disease progression metric (quantitative)

---

## Objective

To build predictive models that estimate disease progression one year after baseline based on patient features, with a focus on evaluating different modeling techniques and understanding their strengths and weaknesses.

---

## Exploratory Data Analysis (EDA)

- **Histograms** to observe distribution of features
- **Scatter plots** of selected features (`bmi`, `sex`, `bp`) vs target
- **Correlation matrix and heatmap** for relationships
- **Insights**:
  - `BMI` and `BP` showed moderate correlation with the target.
  - `Sex` had minimal predictive power.
  - Some features (`s1`-`s6`) were strongly correlated among themselves.

---

## Data Cleaning

- No missing values
- No duplicate entries
- All features are numeric and suitable for modeling

---

## Data Splitting

- **Train set**: 75%
- **Validation set**: 10%
- **Test set**: 15%
- Used `train_test_split` with stratified randomization

---

## Part 2: Univariate Polynomial Regression on BMI

- Built 6 models with polynomial degrees from 0 to 5
- Evaluated using R², MAE, and MAPE
- Best model: **Degree 5**, with:

```text
Test R² = 0.197
Test MAE = 54.55
Test MAPE = 47.88%
```

## Part 2: Univariate Polynomial Regression (BMI Only)

Trained 6 models using BMI with polynomial degrees 0 through 5.

## Part 3:

We used Polynomial Regression (Multivariate), Decision Tree Regression, k-Nearest Neighbors (kNN).

## Conclusion

To conclude:

- **Polynomial Regression (Degree 2 or 3)**: This was performed well, showing good generalization without strong overfitting. Degree 2 had slightly better MAE/MAPE.
- **Decision Trees**: Flexible but showed risk of overfitting beyond depth=3.
- **kNN**: both k=3 and k=7 provided reasonable performance, though sensitive to local data structure.
  Overall, Polynomial Regression (Degree 2) achieved the best balance of accuracy and simplicity in this dataset. Using all features substantially improved performance compared to BMI alone.
