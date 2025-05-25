# Task1
This is the repository of ML Task1 of coding club
## Objective
To perforn EDA on the given dataset, clean it and train an appropriate model to predict whether a student is in romantic relationship or not.

## DATA CLEANING
-- First I identified the null values.(They were present in some columns and in some columns they were not)
-- I filled all the null values with their corresponding mean,median and mode which had highly normalized distribution
-- The columns which were highly correlated with other columnns, for them I had filled the null values as per their relation with other column

## Feature_1, Feature_2 and Feature_3 identification.
-- Using the df[col].describe() I found out the distribution of these 3 columns and their mean,median and mode and also their max and min values.
-- Plotting these 3 columns with other factors like absences, health, Dalc, goout, freetime, etc.
-- I had made boxplots, stacked bar charts, count plots and analysed and deduced what exactly are Feature_1, Feature_2 and Feature_3

## 5 Insightful Questions and Conclusions from them.
-- The questions are as follows:
   -- HOW DOES PARENTS EDUCATION AFFECTS STUDENTS EDUCATION. (Give a Qualitative Analysis.)
   -- HOW DOES GENDER PLAYS A ROLE IN STUDENTS GRADE. DO FEMALES TEND TO STUDY BETTER THAN MALES OR VICE VERSA.
   -- HOW DOES IT AFFECTS THE STUDENTS WHOSE PARENTS ARE APART.
   -- WHAT KIND OF DIFFERENCES IN EDUCATION FACILITIES DO STUDENTS IN RURAL AND URBAN AREAS GET.
-- To answer these questions I had made bar-charts and deduced the insightful conclusions regarding the dataset.

## Model Training for the Dataset to predict the romantic relationship status for a student
-- Since we need to predict yes/no for romantic relationship status we cant use regression models like Linear Regression,etc.
-- We will be using Classifier Models like Naive Bayes Classifier, Logistic Regression(Its name has Regression but it is a classifier model), Random Forest Classifier.
-- The best model will be the one which predicts the romantic status with highest accuracy which has the best precision for both yes and no and most important which is easy interpretable by SHAP and help
   in interpretation of the reason for model predictions.
-- Data is preprocessed with Standard Scaler.
-- Also used Grid Search CV which helps in finding the best set of hyperparameters.
-- I have applied Naive Bayes first. Below is a detailed explanation of what i have done in Naive Bayes.
   -- The target column romantic is encoded as binary.(yes: 1 and no: 0)
   -- Categorical variables are One-Hot-Encoded
   -- Also I have setup a threshold to remove the features which have very low correlation with romantic.
   -- I have describe each model in a more detailed manner in my report file.
-- In Naive Bayes I got a maximum accuracy of 70% and 📉 Confusion Matrix:[[73  9] . The precision for 1 was 67% and for 0 was 71%.
                                                                          [30 18]]
-- But since it would be difficult to apply SHAP to Naive Bayes as it is not a Tree Based Model neither a Differentiable Model.
-- So I further proceeded towards applying Logistic Regression and Random Forest Classifier.
-- In Logistic Regression and Random Forest Classifier I got an accuracy of 62%. I got a precision of 75% for no and 49% for yes in Logistic Regression where as 67% for no and 47% for yes in Random
   Forest Classifier
-- I chose Logistic Regression for further applying SHAP.
## Reasoning and Interpretation of the model using SHAP
-- I chose Feature_1(age) and absences as 2 features for the decision boundary plot.
-- There is also a SHAP Beeswarm plot to indicate global feature importance.
-- Finally generated local explanation for 2 students one predicted yes and one predicted no


________________________________________________________________________________________________________________________________________________________________________________________________________________


*** Dependencies
1. Name: pandas
   Version: 2.2.2
2. Name: numpy
   Version: 2.0.2
3. Name: matplotlib
   Version: 3.10.0
4. Name: seaborn
   Version: 0.13.2
5. Name: scikit-learn
   Version: 1.6.1
6. Name: shap
   Version: 0.47.2
7. Python 3.11.12
