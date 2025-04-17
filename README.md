# 📄 README: Weight Loss Medication Approval Prediction

Welcome to the fun and insightful world of predicting approval for weight loss medications! This project explores how patient survey data can be used to determine the likelihood of being approved for treatment.

---

## 🚀 Project Overview

This case study tackles a real-world classification task: **Can we predict whether a patient will be approved or declined for weight loss medication based on their health and lifestyle data?**

The approach combines:
- Custom data preprocessing
- Feature engineering
- Exploratory data analysis
- Machine learning modeling

---

## 🧾 Dataset Description

The dataset contains patient-submitted survey responses and includes:
- Demographics: height, weight, sex, age
- Health history: mental health conditions, comorbidities
- Lifestyle details: exercise habits, diet quality
- Text-based responses: past weight loss attempts
- Target label: `status` (1 = approved, 0 = declined)

---

## 🛠️ Preprocessing Highlights

Data was cleaned and transformed using a custom-built preprocessing class (`WLIDataPreprocessor`) that:
- Parses list-based fields into binary flags
- Calculates BMI from height and weight
- Counts the number of health-related conditions
- Encodes binary, ordinal, and free-text features
- Removes BMI outliers using IQR filtering

---

## 🔍 Exploratory Analysis

- Visualized BMI distribution to detect and remove outliers
- Explored relationships between health metrics and approval outcomes
- Found trends in lifestyle and mental health indicators

---

## 🔮 Modeling Approach

Performed binary classification using:
- Logistic Regression
- Random Forest

Evaluation metrics:
- Accuracy
- Precision
- Recall
- ROC AUC

The dataset was split into 90% training and 10% test sets.

---

## 💡 Key Takeaways

- **BMI isn’t everything** — other factors like mental health, comorbidities, and lifestyle patterns strongly influence approval.
- **Past efforts matter** — patients who had documented struggles or multiple attempts were more likely to be approved.
- **Feature engineering** made a big difference in capturing the complexity of patient experiences.

---

## 🚀 Deployment Plan

To deploy the model in a real-world environment, here’s a high-level outline:

### 1. Model Serialization
- Use `joblib` or `pickle` to save the trained model and preprocessing pipeline.

### 2. API Creation
- Wrap the model and preprocessing logic in a REST API using **FastAPI** or **Flask**.
- Endpoints:
  - `/predict` — Accepts raw survey inputs, returns predicted approval status
  - `/healthcheck` — For monitoring uptime

### 3. Containerization
- Use Docker to containerize the API for consistent deployment.

### 4. Cloud Hosting
- Deploy to a cloud platform like **AWS (EC2/Fargate)**, **Azure**, or **Heroku**.
- Use load balancing and auto-scaling as needed.

### 5. Monitoring & Logging
- Monitor model performance with tools like **Prometheus**, **Grafana**, or **Sentry**.
- Log predictions and feedback for retraining.

### 6. CI/CD
- Set up automated testing and deployment using **GitHub Actions** or **GitLab CI**.

> 🛡️ Also consider data drift detection and retraining triggers to keep the model accurate over time.

---

## 📈 Future Work

- Test additional models (e.g., XGBoost, LightGBM)
- Use SHAP values to better interpret predictions
- Analyze fairness and bias in model outcomes

---

## 🤖 Requirements

To run the notebook, make sure you have the following installed:
```bash
pandas
numpy
scikit-learn
matplotlib
seaborn
```

---

## 📁 Files
- `Case_study.ipynb`: Main notebook with code and analysis
- `README.md`: This file


