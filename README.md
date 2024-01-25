machine learning project for detection ICU Patient 

##Pre-processing and Feature Engineering:


• Implemented feature selection process, keeping a single feature with a correlation of 1
while discarding others, which resulted in a reduced feature set of 88 variables.
Handling “window”:

• This addressed the temporal aspect of patient records (“window” feature). Using a unique
method we discarded features other than ICU with value of 1 since others were not useful
for prediction, resulting in a dataset reduction to 1605 rows

.Changing categorical to numerical:
• Categorical features like "AGE_PERCENTILE" and "WINDOW" were handled through
dummy variables, after the resolution of the "window" feature, enhancing the dataset's
ability for predictive modeling.
Missing values:

• Initial missing value handling involved Linear Interpolation; however, the feature
"ALBUMIN_DIFF" was dropped due to high missing values. Subsequently, after
addressing skewness, the remaining missing values were resolved using a simple imputer,
resulting in a uniform dataset.
Handling Skewness:

• We implemented two skewness handling techniques, logarithmic transformation for
right-skewed data and reciprocal transformation for left-skewed data. These methods
effectively addressed skewness, optimizing the distribution of features.

• Observing large or infinite values in the "other" column, we dropped it to prevent
potential outlier influence.


##PCA:

Employing PCA, we reduced the dimensionality to 40 components. Temporarily excluding
"gender" and "ICU" for preservation, they were later reintegrated since "gender" was supposed to
undergo ethical addressing using aif360.

##AIF 360:

Two sets of privileged (gender 1) and unprivileged (gender 0) data were created, revealing an
imbalance in the fairness matrix. Initial model evaluation using logistic regression yielded
accuracy of 91%. Subsequent hyperparameter tuning and classification matrix analysis indicated
persistent data imbalance. To address this, the gender feature was temporarily removed, resulting
in decreased accuracy. The gender feature was retained, and reweighing algorithms were applied.
Post-implementation, classification and binary label dataset matrix analyses indicated the
removal of data imbalance without compromising accuracy, a favorable outcome.


##Modelling:

• Dataset was split into train and test, and models like random forest, logistic regression,
and Support Vector Classification were implemented, with the following accuracy:
Model Accuracy
Random Forest 88%
Logistic Regression 86%
Support Vector Classification 89%

• Hyperparameter tuning and model evaluation:
o In this section we used cross validation score and GridSearchCV to compare and
discover the best possible results, although GridSearchCV returned acceptable
accuracy rates, the results with cross validation score were considerably better.
o In conclusion, after Hyperparameter tuning and model evaluation, we reached the
following accuracy rates which were our optimal outcome:
Model Accuracy
Random Forest 90%
Logistic Regression 89%
Support Vector Classification 91%
Comparing the two methods of GridSearchCV and cross validation score, discovered that in
cross validation score, SVC was the best 
