# MIPT International Autumn School 2026 — Machine Learning

A collection of hands-on Jupyter notebooks from the **MIPT International Autumn School 2026**, covering the beginner track of a practical Machine Learning workflow.

The notebooks use a deliberately messy **used-car listings dataset** to demonstrate the complete path from raw data to model selection and evaluation.

## 📚 Course Overview

| Day | Topic | Main Focus |
|---|---|---|
| **Day 1** | Python, pandas & Real Data | Python refresher, NumPy, pandas, data inspection, cleaning and visualization |
| **Day 2** | Models & Metrics | Data splitting, pipelines, regression, classification, evaluation and data leakage |
| **Day 3** | Choosing a Model | Model comparison, cross-validation, tuning, uncertainty and interpretability |

---

## 📁 Notebooks

### 1. `day1_beginner_python_and_data_STUDENT_updated.ipynb`

**Python, pandas and the messy truth about real data**

The first session introduces the dataset and builds the foundation required for Machine Learning.

Topics covered:

- Python fundamentals
  - Lists and dictionaries
  - Loops
  - List and dictionary comprehensions
  - Functions
  - Default arguments
  - Lambda functions
- NumPy
  - Arrays
  - Array operations
  - Boolean masking
  - 2D arrays
  - Shape and statistics
- pandas
  - Loading CSV data
  - Inspecting DataFrames
  - `.head()`
  - `.info()`
  - `.describe()`
  - Missing-value inspection
- Exploratory Data Analysis
- Data cleaning
- Handling inconsistent categorical values
- Missing values and invalid values
- Outlier/data-entry correction
- Feature creation
- Data visualization

### Dataset

The notebook works with **4,255 used-car listings**.

The dataset contains two main targets:

- `price_eur` — regression target: *What should this car cost?*
- `sold_fast` — classification target: *Will this listing sell within 30 days?*

---

### 2. `day2_beginner_models_and_metrics_STUDENT.ipynb`

**Training models properly, and the metrics that tell you whether it worked**

The second session moves from cleaned data to actual Machine Learning models.

Topics covered:

- Deterministic vs. statistical data cleaning
- Train / validation / test splitting
- Preventing data leakage
- `Pipeline`
- `ColumnTransformer`
- `SimpleImputer`
- `StandardScaler`
- `OneHotEncoder`
- Regression
  - Dummy regression baseline
  - Linear Regression
  - Log-target regression
  - Decision Trees
  - Random Forest
- Regression metrics
  - MAE
  - RMSE
  - R²
  - MAPE
- Overfitting
- Training vs. validation performance
- Cross-validation
- Classification
  - Dummy Classifier
  - Logistic Regression
  - Random Forest Classifier
- Classification metrics
  - Accuracy
  - Precision
  - Recall
  - F1-score
  - ROC-AUC
- Confusion Matrix
- ROC Curve
- Classification threshold selection
- Feature leakage
- Honest final test-set evaluation

A major focus of this notebook is understanding **why a model can appear to perform well while actually being unreliable**.

---

### 3. `day3_beginner_choosing_a_model_STUDENT.ipynb`

**Choosing a model, and being able to prove the choice**

The third session focuses on comparing models fairly and defending the final model choice.

Topics covered:

- Reusing the cleaned dataset and train/test split
- Building a common model-comparison framework
- Comparing multiple models on identical data
- Cross-validation
- Measuring fold-to-fold variation
- Understanding whether performance differences are meaningful
- Model candidates:
  - Linear Regression
  - Ridge Regression
  - Decision Tree Regressor
  - Random Forest Regressor
  - HistGradientBoostingRegressor
- Hyperparameter tuning
- `GridSearchCV`
- Coarse parameter search
- Model selection
- Final test-set evaluation
- Model interpretability
- Model coefficients
- Permutation importance
- Project planning and model justification

The central idea is:

> **A model should not be chosen simply because it has the highest score. The difference must be meaningful relative to the uncertainty in the evaluation.**

---

## 🔄 Overall Machine Learning Workflow

The three notebooks together demonstrate a practical workflow:

```text
Raw Dataset
     │
     ▼
Understand the Data
     │
     ▼
Clean & Validate Data
     │
     ▼
Feature Preparation
     │
     ▼
Train / Validation / Test Split
     │
     ▼
Preprocessing Pipeline
     │
     ▼
Baseline Model
     │
     ▼
Train Multiple Models
     │
     ▼
Evaluate with Appropriate Metrics
     │
     ▼
Cross-Validation
     │
     ▼
Compare Models
     │
     ▼
Hyperparameter Tuning
     │
     ▼
Choose Final Model
     │
     ▼
Evaluate Once on Test Set
     │
     ▼
Interpret the Model
     │
     ▼
Project / Real-World Application
```

## 🛠️ Technologies & Libraries

The notebooks primarily use:

- **Python**
- **NumPy**
- **Pandas**
- **Matplotlib**
- **Scikit-learn**
- **Jupyter Notebook / Google Colab**

Important scikit-learn components include:

```text
Pipeline
ColumnTransformer
SimpleImputer
StandardScaler
OneHotEncoder
train_test_split
KFold
cross_val_score
GridSearchCV
LinearRegression
Ridge
DecisionTreeRegressor
RandomForestRegressor
HistGradientBoostingRegressor
LogisticRegression
RandomForestClassifier
DummyRegressor
DummyClassifier
```

## 🎯 Learning Outcomes

After completing these notebooks, the learner should understand how to:

- Work with real-world, imperfect datasets
- Inspect and clean data before modelling
- Distinguish safe cleaning from operations that can cause leakage
- Build preprocessing pipelines
- Separate training, validation and test data
- Establish meaningful baselines
- Train both regression and classification models
- Select appropriate evaluation metrics
- Identify overfitting
- Use cross-validation
- Compare models fairly
- Tune a model without excessive searching
- Detect data leakage
- Evaluate a final model honestly
- Interpret model behaviour
- Use permutation importance
- Defend a model-selection decision using evidence

## 🚗 Dataset Problem

The notebooks use a used-car listing problem as a common Machine Learning case study.

### Regression

**Goal:** Predict the price of a used car.

```text
Features → Car information
Target   → price_eur
```

### Classification

**Goal:** Predict whether a listing will sell within 30 days.

```text
Features → Car information
Target   → sold_fast
```

One important lesson is identifying `days_on_market` as a **leaky feature** for the `sold_fast` prediction task because the target itself is defined using whether the listing sold within 30 days.

## 📌 Key Lessons

### 1. Look at the data before modelling

> **Understand the data before you build the model.**

### 2. Prevent data leakage

Statistical preprocessing such as imputation and scaling should be learned from the training data rather than the entire dataset.

### 3. Always establish a baseline

A sophisticated model should demonstrate that it actually improves on a simple baseline.

### 4. Training performance is not enough

A model that performs extremely well on its training data may simply be memorizing it.

### 5. Use the right metrics

Different problems require different metrics. Accuracy, MAE, RMSE, precision, recall, F1 and ROC-AUC answer different questions.

### 6. Cross-validation gives a more reliable comparison

A small difference between models may simply be caused by variation between different data splits.

### 7. Tune only when it is worth it

Hyperparameter tuning should be controlled and performed after the problem, features and evaluation methodology are established.

### 8. The test set should be protected

The final test set should be used only for the final evaluation rather than repeatedly checking it while selecting a model.

### 9. Choose models for more than performance

When models perform similarly, factors such as interpretability, speed and practical constraints can determine the better choice.

---

## 📂 Repository Structure

```text
.
├── day1_beginner_python_and_data_STUDENT_updated.ipynb
├── day2_beginner_models_and_metrics_STUDENT.ipynb
├── day3_beginner_choosing_a_model_STUDENT.ipynb
└── README.md
```

## 🎓 Program

**MIPT International Autumn School 2026**

This repository documents the practical beginner-track Machine Learning work completed during the program, progressing from **Python and data preparation → model training and evaluation → model selection and interpretation**.

---

### 🚀 Progression

```text
Day 1
Python + NumPy + Pandas
        ↓
Data Cleaning + EDA
        ↓
Day 2
Preprocessing + Pipelines
        ↓
Regression + Classification
        ↓
Metrics + Leakage + Cross-Validation
        ↓
Day 3
Model Comparison
        ↓
Hyperparameter Tuning
        ↓
Model Selection
        ↓
Interpretability
        ↓
Project
```# Machine-Learning-Autumn-Program
This repository documents my learning and project work from the Machine Learning Autumn Programme at Moscow Institute of Physics and Technology (MIPT), Russia, held from 6th September to 14th September 2026.
