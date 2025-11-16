# Project 4 – Predicting Titanic Fare Using Regression

This notebook analyzes the Titanic dataset, focusing on building and comparing regression models.

## Objectives: 
- Importing and inspecting the dataset  
- Preparing data and exploring key features  
- Selecting features for regression modeling  
- Training a baseline Linear Regression model  
- Comparing alternative models: Ridge, Elastic Net, Polynomial Regression  
- Summarizing findings and insights  

## Notebook Structure
The notebook follows this organized workflow:

### 1. Imports  
All imports are grouped in one clean cell, including pandas, numpy, seaborn, matplotlib, and scikit-learn regression tools.

### 2. Import & Inspect Data  
- Loaded the Titanic dataset using seaborn.
- Reviewed the first few rows and confirmed structure.

### 3. Data Exploration & Preparation  
- Filled missing **age** values with the median.  
- Removed rows with missing **fare**.  
- Created a new **family_size** feature using sibsp + parch + 1.  
- Prepared categorical variables when needed.

### 4. Feature Selection  
Created four different feature sets:
- **Case 1:** age  
- **Case 2:** family_size  
- **Case 3:** age + family_size  
- **Case 4:** custom-selected feature(s)  

Each case used its own X and y variables so results could be compared.

### 5. Train & Evaluate Linear Regression Models  
For all four cases:
- Split into train/test sets.  
- Trained Linear Regression models.  
- Calculated R², RMSE, and MAE.  
- Compared train vs test performance to check overfitting or underfitting.

## Compare Alternative Models  
Using the best-performing case, explored:

**Ridge Regression**  
- Used L2 regularization to reduce overfitting.

**Elastic Net Regression**  
- Combined L1 and L2 penalties.

**Polynomial Regression (degree 3)**  
- Added nonlinear relationships using PolynomialFeatures.
- Plotted actual vs predicted values for visualization.
- Expanded to higher-degree polynomial (e.g., 4–8) and compared performance.

## Model Comparison Summary  
Created a summary display for all models:
- Linear Regression  
- Ridge  
- Elastic Net  
- Polynomial Regression  

Compared each using R², RMSE, and MAE.

### 6. Final Thoughts & Insights  
Reflected on:
- Which features worked best  
- Which regression model performed the strongest  
- How regularization and polynomial complexity changed the results  
- Challenges such as skewed fare values and outliers  

## Summary
This project demonstrates the full regression workflow:
- Cleaning and preparing real-world data  
- Experimenting with different feature sets  
- Training and comparing multiple regression models  
- Visualizing model performance  
- Reflecting on how model choices influence predictions  
