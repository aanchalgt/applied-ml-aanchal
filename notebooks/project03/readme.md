# Titanic Survival Prediction - Project 3

**Author:** Aanchal Gupta  
**Date:** 9th November 2025  

---

## Project Overview
This project predicts passenger survival on the Titanic using machine learning classification models. We use three models:

- **Decision Tree (DT)**
- **Support Vector Machine (SVM)**
- **Neural Network (MLP)**

We explore how different input features affect model performance.

---

## Step-by-Step Project Sections

### 1. Import and Inspect the Data
- Loaded the Titanic dataset from the `seaborn` library.
- Displayed the first few rows to check the data.
- Key features include: `age`, `sex`, `sibsp`, `parch`, `fare`, `embarked`, `alone`, `survived`.

---

### 2. Data Exploration and Preparation
- **Missing Values:**
  - Filled missing `age` with the median value.
  - Filled missing `embark_town` with the mode.
- **Feature Engineering:**
  - Created `family_size` = `sibsp + parch + 1`.
  - Converted categorical features (`sex`, `embarked`, `alone`) to numeric values.

---

### 3. Feature Selection and Justification
We created three input cases:

1. **Case 1:** Feature = `alone`  
2. **Case 2:** Feature = `age`  
3. **Case 3:** Features = `age + family_size`

- The target for all cases: `survived`.  
- Case 3 is the most informative because it combines two relevant features.

---

### 4. Train and Evaluate Decision Tree
- Split each dataset into **training (80%)** and **test (20%)** sets using `StratifiedShuffleSplit`.  
- Trained a **Decision Tree** for all three cases.  
- Predicted on training and test sets, evaluated using **classification report** and **confusion matrix**.  
- **Decision Tree Plots:** Visualized the tree structure for each case.  

**Reflection:**  
- Case 1 performed poorly (~62%).  
- Case 2 improved (~70%).  
- Case 3 gave the best results (~81%).

---

### 5. Compare Alternative Models

#### 5.1 Support Vector Machine (SVM)
- Trained SVM models using default RBF kernel.  
- Evaluated test predictions and visualized support vectors.  
- Case 3 showed better separation due to two input features.

#### 5.2 Neural Network (MLP) – Case 3
- Trained a **Multi-Layer Perceptron** with 3 hidden layers (50, 25, 10 neurons).  
- Used `lbfgs` solver and `max_iter=1000` for convergence.  
- Predicted survival on the test set and evaluated accuracy (~81%).  
- Visualized decision boundary to see how the model separates survived vs not-survived passengers.

**Reflection:**  
- Neural Network handled complex patterns better than Decision Tree or SVM.  
- Combining `age` and `family_size` gave the most accurate predictions.

---

### 6. Final Thoughts & Insights

**📋 Summary of Results**

| Case   | Features Used       | Best Model       | Performance (Example Accuracy) | Notes                             |
|--------|-------------------|----------------|-------------------------------|----------------------------------|
| Case 1 | Alone             | Decision Tree  | ~62%                          | Weak predictor on its own        |
| Case 2 | Age               | SVM            | ~70%                          | Better, but still limited        |
| Case 3 | Age + Family Size | Neural Network | ~81%                          | Best results – captures patterns well |

**Challenges Faced:**  
- Some features had missing values that needed imputation.  
- Neural Network needed careful setup (solver, max iterations) to converge.

**Next Steps:**  
- Add more features like `sex`, `pclass`, and `fare`.  
- Experiment with hyperparameters for all models.  
- Use cross-validation to validate model stability.  
- Explore feature scaling to improve SVM performance.

---
