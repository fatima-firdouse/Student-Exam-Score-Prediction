# 🎓 Student Performance Prediction (Regression Project)

## 📌 Project Overview

This project focuses on building an **end-to-end Machine Learning regression pipeline** to predict students' **Final Exam Scores** based on academic, demographic, and behavioral features.

The goal was **not** to chase maximum accuracy, but to deeply understand:

* Regression assumptions
* Feature preprocessing
* Regularization effects
* Model diagnostics and limitations

---

## 🎯 Problem Statement

Predict a **continuous target variable** (`Final_Exam_Score`) using regression techniques.

This is a classic **supervised regression problem** where the output is a numeric value.

---

## 🧠 Learning Objectives

* Perform structured **EDA** to understand data behavior
* Apply correct preprocessing for **numerical vs categorical features**
* Build a reusable **Pipeline + ColumnTransformer**
* Compare **Linear Regression vs Ridge Regression**
* Analyze why performance plateaus instead of blindly adding complexity

---

## 📂 Dataset Description

The dataset contains student-level information such as:

### Numerical Features

* `Study_Hours_per_Week`
* `Attendance_Rate`
* `Past_Exam_Scores`

### Categorical Features

* `Gender`
* `Internet_Access_at_Home`
* `Extracurricular_Activities`
* `Parental_Education_Level` (ordinal)

### Target Variable

* `Final_Exam_Score`

---

## 🔍 Exploratory Data Analysis (EDA)

Key observations from EDA:

* **Attendance Rate** has the strongest relationship with final scores
* Numerical features are reasonably well-distributed
* No severe missing-value issues
* Dataset shows **mostly linear relationships**

This insight later explained why complex models did **not** significantly improve performance.

---

## ⚙️ Preprocessing Strategy

A structured preprocessing pipeline was built using `ColumnTransformer`.

### Numerical Pipeline

* Standard Scaling
* Polynomial Features (degree = 2, tested)

### Ordinal Encoding

* `Parental_Education_Level`

  * High School < Bachelors < Masters < PhD

### Nominal Encoding

* One-Hot Encoding with `drop='first'`

All preprocessing steps were wrapped inside a **single pipeline** to prevent data leakage.

---

## 🤖 Models Used

### 1️⃣ Ridge Regression

* Used to handle potential multicollinearity
* Tested multiple `alpha` values

### 2️⃣ Polynomial Features (Experiment)

* Tested to check non-linearity
* Result: No meaningful improvement → model remained data-limited

---

## 📊 Model Evaluation

Metrics used:

* **RMSE** (Root Mean Squared Error)
* **R² Score**

### Final Performance

* **R² ≈ 0.62**
* Stable across multiple regularization strengths

This stability indicates:

* The dataset is largely linear
* Additional complexity does not improve generalization

---

## 🧪 Generalization Test

Predictions were tested on **new, unseen student data**, confirming:

* Reasonable predictions
* No extreme extrapolation behavior

---

## 🛠️ Tech Stack

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* Scikit-learn

---

## 🚀 Future Improvements

* Try tree-based models (Random Forest, Gradient Boosting)
* Feature importance analysis
* Apply the same pipeline to a different regression domain

---

## 👤 Author

**Fatima Firdouse**
Engineering Student | Aspiring ML / AI Engineer

---

⭐ *This project emphasizes understanding over blind optimization.*
