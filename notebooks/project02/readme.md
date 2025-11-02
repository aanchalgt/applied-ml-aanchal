# Titanic Data Survival Analysis
**Author:** Aanchal Gupta 
**Date:** October 30, 2025  

## Project Summary :

This project investigates the Titanic dataset (from the Seaborn library) to understand which factors influenced passenger survival. The analysis includes exploring the data, creating new features, and preparing it for a classification model.

## Objectives: 
- Examine and understand the structure of the dataset
- Detect missing values and review summary statistics
- Visualize relationships between features
- Engineer features that could improve model performance
- Define predictor variables (X) and the target variable (y)
- Split the dataset into training and testing sets, including a stratified split

## Dataset Details

The dataset contains 891 passengers and 15 features, including:
- survived (0 = no, 1 = yes),
- pclass (passenger class),
- sex,
- age,
- fare,
- sibsp (siblings/spouses aboard),
- parch (parents/children aboard),
- embarked (port of embarkation),
- And additional fields,
- Some columns, such as age and deck, have missing values.

## Analysis Workflow
1. Loading and Inspecting Data:
-Load the Titanic dataset using sns.load_dataset("titanic")
-Review columns, data types, missing values, and summary statistics
-Check correlations between numerical features

2. Exploration and Visualization:
- Scatter plots (e.g., age vs fare, with sex as color)
- Count plots for passenger class and survival
- Histograms for age distribution
- Scatter matrix for numeric features

Insights from visuals:
- First-class passengers had higher survival rates
- Females were more likely to survive than males
- Younger passengers were often in lower classes

3. Feature Engineering: 
- New features were created to improve model performance:
- family_size = sibsp + parch + 1
- sex converted to numeric values (male = 0, female = 1)
- embarked mapped to numeric values
- alone converted from boolean to 0/1

4. Feature Selection:
- The model predicts survived using: age, fare, pclass, sex, famil_size
- The target variable is survived, and the other selected features are used as predictors.

5. Train/Test Splitting :

- Two methods were used to split the data:
Standard train_test_split
StratifiedShuffleSplit to maintain the same survival proportion in training and testing sets

- Stratification was important because the dataset is imbalanced, with more passengers not surviving than surviving.

## Reflections:

-The dataset demonstrates how characteristics like class, gender, and age influence survival.

**Challenges:**
- Handling missing values (especially for age and deck) and converting categorical features into numeric values for modeling.

**Notable observations:**
Females and first-class passengers had higher survival rates, clearly shown in count plots and scatter plots.

**Main takeaway:**
Proper data cleaning and feature selection significantly impact model accuracy. 

## Tools & Libraries
- Python  
- pandas  
- NumPy  
- seaborn  
- matplotlib  
- scikit-learn
