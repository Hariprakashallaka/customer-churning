# Customer Churn Prediction Using Machine Learning

## Project Overview

This project focuses on predicting whether a customer is likely to **churn** or **stay** using machine learning.

The model uses customer behavior and account-related information such as payment delays, support calls, tenure, usage frequency, total spending, age, contract length, and subscription type.

The project follows a complete machine learning workflow, including data preprocessing, exploratory data analysis, feature analysis, model building, hyperparameter tuning, and model evaluation.

---

## Objective

The main objective is to build a classification model that can identify customers who are at higher risk of churn.

This type of prediction can help businesses:

* Identify customers at risk of leaving
* Understand important churn-related factors
* Take proactive customer retention actions
* Improve customer retention strategies

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

---

## Dataset

The dataset contains customer-level information used to predict the target variable:

**Target Variable:** `Churn`

Important features include:

* Payment Delay
* Support Calls
* Tenure
* Usage Frequency
* Total Spend
* Age
* Gender
* Contract Length
* Subscription Type
* Last Interaction

---

## Exploratory Data Analysis

Exploratory Data Analysis was performed to understand:

* Dataset structure
* Numerical and categorical features
* Missing values
* Customer churn distribution
* Relationships between customer behavior and churn
* Important patterns in customer data

---

## Data Preprocessing

The preprocessing workflow included:

* Separating features and target variable
* Handling numerical and categorical features
* Encoding categorical variables using One-Hot Encoding
* Splitting the dataset into training and testing sets
* Building a preprocessing pipeline using Scikit-learn

---

## Machine Learning Models

Two classification algorithms were evaluated:

### 1. Decision Tree

A Decision Tree was used as a baseline classification model.

### 2. Random Forest

Random Forest was then used to improve model performance by combining multiple decision trees.

---

## Hyperparameter Tuning

Random Forest hyperparameters were optimized using:

**GridSearchCV with 5-fold cross-validation**

The selected parameters were:

```text
n_estimators = 100
max_depth = None
max_features = None
min_samples_split = 2
min_samples_leaf = 2
```

---

## Model Performance

The tuned Random Forest achieved:

| Metric    |     Score |
| --------- | --------: |
| Accuracy  |    99.92% |
| Precision |    99.87% |
| Recall    |    99.97% |
| F1-Score  |    99.92% |
| ROC-AUC   | ~0.999996 |

### Confusion Matrix

```text
TN = 6768
FP = 8
FN = 2
TP = 6097
```

The model produced only **10 incorrect predictions out of 12,875 test samples**.

---

## Feature Importance

Feature importance analysis showed that:

1. Payment Delay
2. Support Calls
3. Tenure
4. Usage Frequency
5. Total Spend
6. Age

were among the most influential features for the model.

`Payment Delay` had the highest model-derived feature importance.

> Feature importance indicates predictive contribution to the model. It does not mean that a feature causally produces churn.

---

## Feature Ablation Analysis

To understand the influence of `Payment Delay`, the model was also evaluated without this feature.

The test accuracy decreased substantially to approximately:

**78.08%**

This demonstrates that `Payment Delay` contains a very strong predictive signal in this dataset.

Because the overall model performance is unusually high, the availability and meaning of `Payment Delay` should be validated carefully before using the model in a real-world production environment.

---

## Business Insights

The analysis suggests that businesses should pay particular attention to customers showing:

* High payment delays
* Frequent support calls
* Lower engagement or usage
* Shorter tenure
* Changes in spending behavior

These signals can potentially be used to identify customers who may require retention efforts.

---

## Project Workflow

```text
Data Collection
      ↓
Data Cleaning
      ↓
Exploratory Data Analysis
      ↓
Feature Preprocessing
      ↓
Train-Test Split
      ↓
Decision Tree
      ↓
Random Forest
      ↓
Hyperparameter Tuning
      ↓
Model Evaluation
      ↓
Feature Importance
      ↓
Business Insights
```

---

## Project Structure

```text
customer-churning/
│
├── data/
│   └── customer_churn.csv
│
├── notebooks/
│   └── customer_churn_analysis.ipynb
│
├── images/
│   ├── eda.png
│   ├── confusion_matrix.png
│   ├── roc_curve.png
│   └── feature_importance.png
│
├── src/
│   ├── preprocessing.py
│   ├── train.py
│   └── evaluate.py
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone https://github.com/Hariprakashallaka/customer-churning.git
```

### 2. Navigate to the project

```bash
cd customer-churning
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Open the notebook

```bash
jupyter notebook
```

Open the customer churn analysis notebook and run the cells.

---

## 👨‍💻 Author

**Hariprakash Allaka**

GitHub: `Hariprakashallaka`
