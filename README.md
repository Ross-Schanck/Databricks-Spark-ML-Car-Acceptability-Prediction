# Car Evaluation Classification Using Spark MLlib

## Project Overview
This project builds and evaluates multiple machine learning models using Databricks and Apache Spark MLlib. The goal is to predict the acceptability of a car based on its features such as price, maintenance cost, number of doors, passenger capacity, trunk size, and safety.

The dataset used is the **Car Evaluation dataset** from the UCI Machine Learning Repository.

This project demonstrates a complete end-to-end machine learning workflow, including data engineering, feature engineering, model training, evaluation, and experiment tracking using MLflow.

---

## Dataset Description
The dataset contains categorical attributes that describe car characteristics and a target label indicating car acceptability.

### Features include:
- Buying price
- Maintenance cost
- Number of doors
- Passenger capacity
- Trunk size
- Safety rating

### Target Variable:
- Car Acceptability (unacceptable, acceptable, good, very good)

---

## Data Engineering & Feature Engineering

### Schema Definition
- The dataset was loaded with a defined schema to ensure proper data structure.

### Feature Engineering
Two engineered features were created:
- `doors_num`: Converted “5more” into numeric value 5
- `capacity_label`: Combined passenger capacity and trunk size into a single feature

---

## Data Preprocessing

The following preprocessing steps were applied:

- Categorical encoding using:
  - StringIndexer
  - OneHotEncoder
- Numerical scaling using StandardScaler
- Feature assembly into a single vector for model input

---

## Train/Test/Validation Split

The dataset was split into:
- 72% Training set
- 18% Test set
- 10% Validation set

A two-step splitting process was used to ensure the validation set remained untouched during training.

---

## Machine Learning Models

Three classification models were trained and evaluated:

- Logistic Regression
- Random Forest
- Gradient Boosted Trees (GBT)

---

## Model Evaluation

Models were evaluated using:
- Accuracy
- F1 Score

### Results:

| Model                | Accuracy | Performance Summary |
|---------------------|----------|---------------------|
| Logistic Regression | 0.9333   | Best overall model, strong balance of accuracy and simplicity |
| Gradient Boosted Trees | 0.9296 | Close second, strong performance |
| Random Forest       | 0.7889   | Underperformed compared to other models |

---

## Final Model Selection

Logistic Regression was selected as the best-performing model due to:
- Highest accuracy
- Strong F1 score
- Simplicity and interpretability

---

## MLflow Experiment Tracking

MLflow was used to track:
- Model parameters
- Accuracy and F1 scores
- Trained model artifacts

The MLflow UI was used to compare models and confirm experiment tracking consistency.

---

## Key Takeaways

- Spark MLlib enables scalable machine learning workflows
- Feature engineering significantly improves model performance
- Simpler models (Logistic Regression) can outperform complex models on structured categorical datasets
- MLflow improves reproducibility and experiment tracking

---

## Conclusion

This project demonstrates a full machine learning pipeline using Databricks and Spark MLlib, from data preprocessing to model evaluation and experiment tracking. Logistic Regression proved to be the most effective model for this dataset due to its balance of accuracy and interpretability.
