# Cardiovascular Disease Classification

## Problem Statement
Heart health has always been a critical topic, and early diagnosis can be life-saving. I chose to work on cardiovascular disease classification because of its real-world impact—accurately identifying those at risk can make a significant difference. The dataset, sourced from [Kaggle](https://www.kaggle.com), includes various patient metrics, such as age, cholesterol levels, and blood pressure, with the goal of predicting the presence (`1`) or absence (`0`) of cardiovascular disease.

## Objective
The objective of this project was clear: develop a model that prioritizes **recall for class 1**, ensuring that people with cardiovascular disease are correctly identified. Minimizing false negatives is crucial because predicting a person as healthy when they have a condition could lead to serious consequences. Through this project, I aimed to find the best classification model to support early detection efforts.

This version adds a personal touch and highlights your motivation behind the project.


## Dataset Description
The dataset consists of 68,205 rows and 17 columns. Below is an overview of the key features:

- **Age**: Age of the individual in days (integer)
- **Height**: Height in centimeters (integer)
- **Weight**: Weight in kilograms (float)
- **Gender**: Gender of the individual (categorical code)
- **Systolic Blood Pressure (ap_hi)**: Systolic blood pressure (integer)
- **Diastolic Blood Pressure (ap_lo)**: Diastolic blood pressure (integer)
- **Cholesterol**: Cholesterol level, categorized as 1 (normal), 2 (above normal), 3 (well above normal)
- **Glucose**: Glucose level, categorized as 1 (normal), 2 (above normal), 3 (well above normal)
- **Smoking**: Smoking status (binary)
- **Alcohol Intake**: Alcohol consumption status (binary)
- **Physical Activity**: Whether the individual engages in physical activity (binary)
- **Cardio**: Target variable representing cardiovascular disease status (binary, 0 for no disease, 1 for presence of disease)

## Exploratory Data Analysis (EDA)
- The dataset contains 15 numeric and 2 categorical features.
- No missing values were detected in the dataset.
- The features `id` and `bp_category_encoded` were excluded, as they do not contribute meaningfully to the analysis.
- A strong correlation was identified between `age` (in days) and `age_years`, leading to the removal of the `age` (in days) column to avoid redundancy.

## Data Preprocessing
1. **Data Splitting**: The dataset was split into 80% for training and 20% for testing.
2. **Feature Engineering**:
   - One-Hot Encoding (OHE) was applied to the `bp_category` variable.

## Modeling & Evaluation
A total of 14 machine learning models were implemented and categorized into non-ensemble and ensemble models. 
<img width="1354" alt="image" src="https://github.com/user-attachments/assets/13d98a7e-0ef1-43e7-bdc3-73c668a9f5aa">

The performance of these models was evaluated using **recall for class 1**, focusing on minimizing false negatives. 

The best-performing model was the **Decision Tree Classifier**, which achieved a recall of **0.71** for class 1. This model was optimized using **GridSearchCV** with the following parameters:
- **Criterion**: Entropy
- **Max Depth**: 4

Bagging with the Decision Tree model also yielded similar results, but the simpler Decision Tree model was selected due to its efficiency and performance. 

## Conclusion
The Decision Tree Classifier with GridSearchCV was identified as the best model for cardiovascular disease classification. With a **recall of 0.71** for class 1, it effectively minimizes false negatives, making it a reliable choice for medical diagnosis. 

This project demonstrates that using simple yet powerful models like Decision Trees, combined with careful tuning, can provide accurate and interpretable results for health-related classification problems.
