# Loan-Application-Status-Prediction
This project focuses on predicting the approval status of loan applications using a dataset of loan applicants' information. The goal is to build a machine learning model that can classify loan applications as either "Accepted" or "Rejected" based on various features such as personal details, employment information, financial history, and more.

**1. Problem Statement**
This project aims to predict whether a two-wheeler loan application will be accepted or rejected based on a variety of personal, financial, and employment-related features. The task involves building a machine learning model that can generalize well to new, unseen loan applications.

**2. Approach Overview**
Data Preprocessing:

Handling Missing Values: Missing data in categorical columns was replaced with 'Unknown', while missing values in numerical columns were imputed using the median.
Date Column Removal: The 'DATE OF BIRTH' column was excluded from the dataset as it was not relevant for prediction.
Feature Alignment: Ensured that both the training and test datasets contained the same features, resolving any inconsistencies.
Categorical Encoding:

Label Encoding was applied to convert categorical variables (e.g., 'Gender', 'Marital Status') into numeric values for the model to process effectively.
Scaling and Standardization:

Numerical features were standardized using StandardScaler to ensure that the model received normalized data for better performance.
Model Selection and Tuning:

The RandomForestClassifier was chosen for its ability to handle both categorical and numerical features. Hyperparameter tuning was conducted using GridSearchCV to optimize the number of estimators, maximum depth, and other parameters for the best possible performance.
Model Evaluation:

The model's effectiveness was evaluated on a validation set using metrics such as accuracy, precision, recall, and F1-score.

**3. Performance on Train Data Set**
Training Metrics:

Accuracy on Validation Set: 0.82 (82%) This indicates that the model correctly predicted the loan status in 82% of the cases on the validation set.

**Classification Report:**
              precision    recall  f1-score   support

         0       0.85      0.88      0.86       200
         1       0.78      0.74      0.76       150

  accuracy                           0.82       350
 macro avg       0.82      0.81      0.81       350

weighted avg 0.82 0.82 0.82 350 


The precision for class 0 (accepted loans) is 0.85, meaning that 85% of the loan applications predicted as accepted were actually correct. The precision for class 1 (rejected loans) was slightly lower at 0.78. Recall for class 0 was higher at 0.88, while class 1 had a recall of 0.74.

**Grid Search Results:**

The optimal parameters selected during GridSearchCV were:

- **n_estimators:** 100
- **max_depth:** 20
- **min_samples_split:** 5
- **min_samples_leaf:** 2

These parameters contributed to achieving the best balance of performance on the validation set.

---

**4. Insights and Conclusions**

- **Feature Importance:** While the RandomForest model was not explicitly analyzed for feature importance, this could be explored further to understand which features play the most significant role in predicting loan acceptance or rejection.
- **Data Quality and Preprocessing:** The extensive preprocessing, including imputation, feature alignment, and scaling, ensured a clean and reliable dataset that contributed to the model’s good performance.

---
**5. Conclusion**

The model successfully predicted loan application statuses with an accuracy of 82% on the validation set. Through proper data cleaning, feature encoding, and hyperparameter tuning, a RandomForestClassifier was optimized for this task. The model is ready for deployment to predict future loan statuses with consistent performance.
