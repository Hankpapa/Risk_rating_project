# Abstract 
This project employs a computer program that considers 128 continuous variables and 4 categorical factors to evaluate risk for a company when it has new clients. The program utilizes a variety of methods, such as random forest, XGboost, and neural networks, and the data is improved through processes like outlier removal, missing data handling, and feature selection. In multi-class classification, the program achieves an overall accuracy rate of approximately 23%, with particular attention to the significance of BRcode 12 and Variable_17_Y0 in making risk assessments. These methods have the potential to assist the company in identifying and managing risk among new clients, thereby minimizing potential losses and maximizing profits with safer clients.
# Intorduction 
The project employs machine learning to forecast the risk rating of new clients. It achieves this by training on a dataset consisting of 121 independent variables and 4 categorical variables, which can be found in the original data located at /dataset/raw data/df_client.csv. The task is separated into four steps: <br />
 - 1. Exploratory Data Analysis (EDA) <br />
 - 2. Model engineering
 - 3. Model fitting
 - 4. Deep learning 
# EDA
In this section, I provide the basic information of the dataset including the total number of samples, distribution of target variables, and Correlation between features. The plot was generated by Tableau.
# Model engineering
In this part, I followed each step of the data progress: <br />
 1.  Removing outlier and error data: <br />
     - Dropping the data without the range of 2 standard deviations with mean.
     - Dropping all missing value data.
 2.  Handling the missing data:<br />
     - Using 4 ways on missing data: dropping more than 20% of missing data columns, imputation with mean, imputation with median, and imputation with regression.
     - Each way was applied independently and created 4 datasets. They would be evaluated by the decision tree for selection later.
 3. Dropping the high correlation feature:<br />
     - Using matplotlib and seaborn generated heatmaps for each dataset to remove the features, which are higher than 0.7 in correlation.
 4. ANOVA and Kendall's rank:<br />
     - Employed those two methods to filter the irrelevant features
 5. Standard Scaled
 6. One-hot encoding
 7. label encoding
 8. Train-validation-test split
 9. evaluating the datasets by decision tree:<br />
    - Imputation with regression achieved the highest F1 score. This dataset would move forward.
# Model fitting 
XGBoost and Random Forest have outstanding performance. For higher accuracy, Both models tuned with GridSearchCV, One Vs One, and One Vs Rest. The F1 score is around 23% in both methods. BR code 12 and Variable_17_Y0 have larger significance.
# Deep learning
We trained a Neural Network with varying numbers of hidden layers, ranging from 1 to 5. To optimize the model's hyperparameters, we utilized GridSearchCV. The resulting accuracy we achieved was approximately 23%.
