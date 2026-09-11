# Breast Cancer Prediction using Machine Learning

## Project Date

**May 2026**

## Overview

This project focuses on the development of a Machine Learning-based decision support system for breast cancer prediction using biomedical variables. The objective is not to replace medical diagnosis, but to evaluate how supervised learning models can help distinguish between healthy patients and patients diagnosed with breast cancer based on clinical and blood biomarker data.

The project includes a complete Machine Learning workflow: exploratory data analysis, preprocessing, model training, hyperparameter tuning, evaluation with medical metrics, and deployment through a Streamlit web application.

## Project Context

Breast cancer early detection is a major healthcare challenge. Traditional screening methods such as mammography, ultrasound, and MRI are widely used, but they may present limitations depending on access, cost, and clinical context.

This project investigates the following question:

> Can Machine Learning techniques effectively detect breast cancer using blood biomarkers and clinical data?

## Dataset

The dataset used in this project contains biomedical information related to breast cancer detection.

* Number of observations: **116**
* Number of explanatory variables: **9**
* Target variable: **Classification**
* Classes:
  * `0`: Healthy
  * `1`: Breast cancer

Main variables used:

* Age
* BMI
* Glucose
* Insulin
* HOMA
* Leptin
* Adiponectin
* Resistin
* MCP.1

## Methodology

The project follows a complete supervised Machine Learning pipeline:

1. Data loading and target recoding
2. Exploratory Data Analysis
3. Correlation analysis and biomarker distribution study
4. Train/test split with stratification
5. Feature standardization
6. Model training using pipelines
7. Hyperparameter tuning with GridSearchCV
8. Model evaluation using medical metrics
9. Selection of the best-performing model
10. Deployment with Streamlit

## Models Compared

Six supervised classification models were trained and compared:

| Model                | Purpose                               |
| -------------------- | ------------------------------------- |
| Logistic Regression  | Interpretable baseline model          |
| Naive Bayes          | Probabilistic classification          |
| Ridge Classifier     | Handling collinearity                 |
| Lasso                | Feature selection                     |
| K-Nearest Neighbors  | Local similarity-based classification |
| MLP Classifier       | Neural network approach               |

A DummyClassifier was also used as a naive baseline to verify that the trained models perform better than a simple majority-class strategy.

## Evaluation Metrics

Since this is a medical classification problem, accuracy alone is not sufficient. The evaluation focuses on metrics that are more relevant in healthcare contexts:

* Accuracy
* Balanced Accuracy
* Recall / Sensitivity
* Specificity
* Precision
* F1-score
* AUC-ROC
* False Negatives
* False Positives
* Matthews Correlation Coefficient

## Results

The best-performing model on the test set was **K-Nearest Neighbors (KNN)**.

| Metric               |  Value |
| -------------------- | -----: |
| Accuracy             | 79.17% |
| Recall / Sensitivity | 76.92% |
| Specificity          | 81.82% |
| F1-score             | 80.00% |

The model selection was based on the best compromise between detecting cancer cases and limiting false alerts.

## Streamlit Application

A Streamlit application was developed to make the model accessible through a simple user interface. The user can enter patient biomarker values and obtain a prediction result.

Main features:

* Manual input of patient biomedical variables
* Automatic preprocessing using the trained scaler
* Prediction using the saved Machine Learning model
* Display of the predicted class
* Simple and interactive interface

## Screenshots

### Streamlit Prediction Interface

![Streamlit App](streamlit_app.png)

### Prediction Result

![Prediction Result](prediction_result.png)

### Model Comparison

![Model Comparison](model_comparison.png)

### Confusion Matrix or ROC Curve

![Model Evaluation](model_evaluation.png)

## Project Structure

```text
.
├── README.md
├── app.py
├── breast_cancer_modeling.ipynb.ipynb
├── breast_cancer_presentation.pdf
├── breast_cancer_report.pdf
├── dataR2.csv
├── model.pkl
├── scaler.pkl
├── requirements.txt
├── model_comparison.png
├── model_evaluation.png
├── prediction_result.png
└── streamlit_app.png
