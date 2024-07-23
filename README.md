# 🦠 Machine-Learning-Covid19

This repository contains a machine learning project aimed at detecting the likelihood of COVID-19 patients requiring ICU support. Utilizing a range of preprocessing, feature engineering, and modeling techniques, this project strives to improve predictive accuracy and aid in better healthcare management.

## 📚 Features and Preprocessing

### Preprocessing and Feature Engineering

- **Feature Selection**: Implemented a feature selection process, retaining a single feature with a correlation of 1 and discarding others, reducing the feature set to 88 variables.
- **Handling "Window" Feature**: Addressed the temporal aspect of patient records, discarding non-essential features to focus on critical predictive variables, resulting in 1605 data rows.
- **Categorical to Numerical**: Transformed categorical features such as "AGE_PERCENTILE" and "WINDOW" using dummy variables, enhancing predictive modeling capabilities.
- **Missing Values**: Addressed using Linear Interpolation; features with high missing values like "ALBUMIN_DIFF" were dropped. Remaining missing values were handled using a simple imputer after addressing skewness.
- **Handling Skewness**: Applied logarithmic transformations for right-skewed data and reciprocal transformations for left-skewed data to optimize feature distribution.

### Principal Component Analysis (PCA)

- **PCA Implementation**: Employed PCA to reduce dimensionality to 40 components, excluding "gender" and "ICU" temporarily for ethical considerations and later reintegrating them.

### AI Fairness and Ethics (AIF 360)

- **Fairness Matrix Analysis**: Created sets of privileged (gender 1) and unprivileged (gender 0) data, revealing an imbalance in fairness metrics.
- **Model Evaluation**: Initial logistic regression model achieved 91% accuracy. After hyperparameter tuning, the gender feature was addressed without compromising accuracy using reweighing algorithms.

## 🤖 Modeling and Results

- **Models Implemented**: Random Forest, Logistic Regression, and Support Vector Classification.
- **Hyperparameter Tuning and Model Evaluation**:
  - Utilized cross-validation scores and GridSearchCV to fine-tune and select the best model configurations.
  - Achieved optimal accuracies with Random Forest (90%), Logistic Regression (89%), and Support Vector Classification (91%).


