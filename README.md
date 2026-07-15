# Credit Card Approval Prediction System

An end-to-end Machine Learning system that predicts whether a credit card applicant should be approved or rejected based on their demographic and financial profile. This project covers the entire ML lifecycle—from longitudinal label engineering and class-imbalanced model training to serving predictions via a lightweight Flask web application.

---

## 📂 1. Project Directory Structure

The project workspace is organized as follows:

```text
credit_card_project/
├── data/
│   ├── application_record.csv   # Applicant demographic data
│   └── credit_record.csv        # Monthly payment history logs
├── models/
│   └── card_model.joblib        # Serialized winning model weights
├── templates/
│   └── index.html               # Frontend HTML form UI
├── static/
│   ├── style.css                # Interface styling
│   └── script.js                # Asynchronous API frontend logic
├── notebook.ipynb               # Jupyter Notebook for EDA & prototyping
└── app.py                       # Flask web server backend
