Project Overview
The workflow includes:
Data loading from a public dataset
Data cleaning and preprocessing
   Exploratory Data Analysis (EDA)
   Outlier detection and removal using IQR
   Feature scaling using MinMaxScaler
   Handling class imbalance using SMOTE
   Training multiple ML models
   Hyerparameter tuning using GridSearchCV

Model evaluation using:
  Accuracy Score
  Classification Report
  Confusion Matrix
  Saving the best trained models using Joblib


Dataset
Dataset Source:
https://raw.githubusercontent.com/rashakil-ds/Public-Datasets/refs/heads/main/Bank%20Data.csv
  Target Variable:
   Credit_Mix
   Data Cleaning

The following columns are removed:
  ID
  Month
  Name
  Age
  SSN
  Occupation
  Num_Bank_Accounts
  Type_of_Loan
  Num_Credit_Inquiries
  Payment_of_Min_Amount
  Total_EMI_per_month
  Changed_Credit_Limit
  Monthly_Balance

Missing values are removed using:
df.dropna(inplace=True)

Exploratory Data Analysis (EDA)
The project includes:
  Histogram Analysis
  Distribution Analysis
  Pair Plot
  Count Plot
  Correlation Heatmap
  Box Plot
  Automated Profiling Report

Libraries Used:

   matplotlib
   seaborn
   ydata_profiling

Outlier Removal
Interquartile Range (IQR) method is used.

Formula:
IQR = Q3 - Q1

Outliers are removed using:
df_no_outliers = df[
~((df < (Q1 - 1.5 * IQR)) |
(df > (Q3 + 1.5 * IQR))).any(axis=1)
]

Feature Scaling
Min-Max Normalization:

MinMaxScaler()
Range:
0 to 1


Data Balancing
SMOTE (Synthetic Minority Oversampling Technique) is applied.
SMOTE()
Purpose:

  Balance class distribution
  Improve model performance
  Reduce bias


Data Splitting
  Dataset Split:
       Training : 70%
       Testing  : 15%
       Validation : 15%


Machine Learning Models
   Decision Tree Classifier
   DecisionTreeClassifier()
   Hyperparameter Tuning:
         criterion
         splitter
         max_depth
         min_samples_split
         min_samples_leaf
         max_features
         max_leaf_nodes
         class_weight
         ccp_alpha


Random Forest Classifier
   RandomForestClassifier()
   Hyperparameter Tuning:
        n_estimators
        max_depth
        min_samples_split
        min_samples_leaf
        max_features
        bootstrap
        criterion


XGBoost Classifier
    XGBClassifier()
    Hyperparameter Tuning:
          max_depth
          learning_rate
          n_estimators
          subsample
          colsample_bytree


Evaluation Metrics
      The following metrics are used:
                Accuracy Score
                accuracy_score()
                Classification Report
                classification_report()
                Includes:
                Precision
                Recall
                F1-Score
                Support
                Confusion Matrix
                confusion_matrix()


Hyperparameter Optimization
      Grid Search Cross Validation:
                 GridSearchCV()
                Benefits:
                Finds optimal parameters
                Improves generalization
                Reduces overfitting


Technologies Used
         Python
         Pandas
         NumPy
         Matplotlib
         Seaborn
         Scikit-Learn
         XGBoost
         Imbalanced-Learn
         Joblib
         YData Profiling


Future Improvements
      Feature Selection using PCA
      SHAP Explainability
      Ensemble Learning
      Deep Learning Models
      Streamlit Deployment
      Flask/FastAPI API Development
  
