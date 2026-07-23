# Machine-Learning-Pipeline-ColumnTransformer-Ensemble-Learning-Random-Forest-Classifier
This repository demonstrates the implementation of a complete **Machine Learning workflow** using Scikit-Learn
Machine Learning Pipeline
- ColumnTransformer
- Ensemble Learning
- Random Forest Classifier
- Data Preprocessing
- Model Training
- Hyperparameter Tuning
- Model Evaluation

The objective is to build a clean, reusable, and production-ready machine learning workflow.

---

# 📚 Table of Contents

- Project Structure
- Machine Learning Pipeline
- ColumnTransformer
- Ensemble Learning
- Random Forest Classifier
- Installation
- Dataset
- Data Preprocessing
- Model Training
- Hyperparameter Tuning
- Model Evaluation
- Advantages
- Applications
- Future Improvements

---

# 📁 Project Structure

```text
ML-Pipeline-RandomForest/
│
├── dataset.csv
├── Pipeline_ColumnTransformer.ipynb
├── RandomForest_Classifier.ipynb
├── requirements.txt
├── README.md
└── images/
```

---

# ⚙️ Installation

Clone the repository

```bash
git clone https://github.com/yourusername/ML-Pipeline-RandomForest.git
```

Move into the project directory

```bash
cd ML-Pipeline-RandomForest
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

# 📦 Required Libraries

```python
numpy
pandas
matplotlib
seaborn
scikit-learn
```

Install manually

```bash
pip install numpy pandas matplotlib seaborn scikit-learn
```

---

# 📊 Dataset

You can use any classification dataset.

Examples:

- Titanic Dataset
- Heart Disease Dataset
- Breast Cancer Dataset
- Bank Marketing Dataset
- Customer Churn Dataset
- Adult Income Dataset

---

# 🔹 Machine Learning Pipeline

## What is a Pipeline?

A **Pipeline** is a Scikit-Learn object that combines multiple preprocessing steps and a machine learning model into one workflow.

Instead of writing multiple preprocessing steps separately, Pipeline executes them in order.

---

## Why Use a Pipeline?

- Cleaner code
- Reduces data leakage
- Easier model deployment
- Reusable workflow
- Simplifies hyperparameter tuning
- Easy integration with GridSearchCV

---

## Pipeline Workflow

```text
Dataset
     │
     ▼
Missing Value Handling
     │
     ▼
Encoding
     │
     ▼
Feature Scaling
     │
     ▼
Machine Learning Model
     │
     ▼
Prediction
```

---

## Example

```python
from sklearn.pipeline import Pipeline

pipeline = Pipeline([
    ("scaler", StandardScaler()),
    ("model", RandomForestClassifier())
])
```

---

# 🔹 ColumnTransformer

## What is ColumnTransformer?

ColumnTransformer allows different preprocessing techniques to be applied to different columns.

Example:

- Numerical columns → StandardScaler
- Categorical columns → OneHotEncoder

---

## Why Use ColumnTransformer?

- Handles mixed data types
- Performs preprocessing in one step
- Prevents manual errors
- Works seamlessly with Pipeline

---

## Workflow

```text
Dataset
      │
      ├──────────────┐
      │              │
      ▼              ▼
Numerical      Categorical
Columns          Columns
      │              │
StandardScaler  OneHotEncoder
      │              │
      └──────┬───────┘
             ▼
     Combined Features
```

---

## Example

```python
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import StandardScaler
from sklearn.preprocessing import OneHotEncoder

preprocessor = ColumnTransformer([
    ("num", StandardScaler(), numerical_columns),
    ("cat", OneHotEncoder(), categorical_columns)
])
```

---

# 🔹 Ensemble Learning

## What is Ensemble Learning?

Ensemble Learning combines multiple machine learning models to produce a stronger and more accurate model.

Instead of relying on one model, multiple models work together.

---

## Types of Ensemble Learning

### 1. Bagging

Models are trained independently on different random subsets of the data.

Examples:

- Random Forest
- Bagging Classifier

---

### 2. Boosting

Models are trained sequentially, where each new model corrects the mistakes of the previous one.

Examples:

- AdaBoost
- Gradient Boosting
- XGBoost
- LightGBM
- CatBoost

---

### 3. Voting

Multiple classifiers vote for the final prediction.

Examples:

- Hard Voting
- Soft Voting

---

### 4. Stacking

Predictions from multiple models are used as input to another model (meta-model).

---

## Advantages of Ensemble Learning

- Higher accuracy
- Better generalization
- Reduced overfitting
- Improved robustness
- Better predictive performance

---

# 🌲 Random Forest Classifier

## What is Random Forest?

Random Forest is a supervised machine learning algorithm based on **Bagging**.

It creates multiple Decision Trees and combines their predictions using majority voting.

---

## Workflow

```text
Training Data
       │
       ▼
Bootstrap Sampling
       │
       ▼
Decision Tree 1
Decision Tree 2
Decision Tree 3
Decision Tree N
       │
       ▼
Majority Voting
       │
       ▼
Final Prediction
```

---
