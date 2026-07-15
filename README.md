# Credit Card Approval Prediction System

An end-to-end Machine Learning system that predicts whether a credit card applicant should be approved or rejected based on their demographic and financial profile. This project covers the entire ML lifecycle—from longitudinal label engineering and class-imbalanced model training to serving predictions via a lightweight Flask web application.

---
📌 Project Overview
Credit Card Approval Prediction is a Machine Learning project developed to automate the credit card approval process used by banks and financial institutions. The system analyzes applicant information such as income, employment status, age, credit history, and other financial factors to predict whether a credit card application should be approved or rejected.

The project aims to reduce manual effort, improve decision-making accuracy, minimize human errors, and provide faster approval decisions.

🎯 Problem Statement
Banks and financial institutions receive a large number of credit card applications every day. Evaluating each application manually requires analyzing multiple applicant details, including:

Income Level
Employment Status
Age
Credit Score
Existing Loans
Repayment History
Financial Stability
Manual verification is time-consuming, costly, and prone to inconsistencies. Delays in approval decisions can negatively affect customer satisfaction.

To address these challenges, this project develops an intelligent machine learning-based system capable of predicting whether a credit card application should be approved or rejected based on historical customer data.

💡 Ideation and Project Selection
Several project ideas related to Banking and Finance were evaluated:

S.No	Project Idea
1	Credit Card Approval Prediction
2	Loan Eligibility Prediction System
3	Credit Risk Assessment System
4	Customer Credit Score Prediction
5	Credit Card Fraud Detection using Machine Learning
6	Personal Loan Recommendation System
Prioritization Result
Project Idea	Feasibility	Importance	Priority	Selected
Credit Card Approval Prediction	High	High	1	Yes
Loan Eligibility Prediction	High	Medium	2	No
Credit Risk Assessment System	Medium	High	3	No
The Credit Card Approval Prediction project was selected because it solves a practical banking problem, offers high business value, and can be effectively implemented using Machine Learning techniques.

👤 Target Users
Credit Card Applicants
Banks
Financial Institutions
Loan Officers
Credit Analysts

🧠 Empathy Map Analysis
Customer: Credit Card Applicant
Says
"I need a credit card for my daily and emergency expenses."
"Will my application be approved?"
"I hope the approval process is quick."
"I want a transparent approval process."
Thinks
"Do I meet the bank's eligibility criteria?"
"My credit score and income should be sufficient."
"I don't want my application to be rejected without a reason."
Does
Applies for a credit card online or at a bank.
Uploads identity and income documents.
Checks application status regularly.
Maintains a good credit history.
Feels
Anxious while waiting for approval.
Hopeful about approval.
Confused if applications are delayed.
Satisfied when decisions are transparent and fast.
Pain Points
Lengthy approval process.
Lack of transparency.
Rejection due to poor credit history.
Delays caused by manual verification.
Gains
Faster approval decisions.
Accurate evaluation using Machine Learning.
Reduced waiting time.
Better customer experience.

🚀 Proposed Solution
The proposed solution uses Machine Learning algorithms to automatically evaluate credit card applications based on applicant information.

The system:

Accepts applicant details.
Preprocesses and validates the data.
Uses a trained Machine Learning model to predict approval status.
Displays the approval decision instantly.
This helps banks make faster, more accurate, and consistent approval decisions.

🏗️ Technology Stack
Programming Language
Python
Machine Learning Libraries
Scikit-learn
Pandas
NumPy
Joblib
Web Framework
Flask
Frontend
HTML
CSS
Deployment
IBM Watson Machine Learning (Optional)
Flask Web Application

## 📂 Project Directory Structure

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

## 2. Install dependencies

```bash
pip install -r requirements.txt
```

## 3. Train the model

```bash
python train.py
```

This reads the two CSVs, builds the `TARGET` label (1 = risky/rejected if
the applicant was ever 60+ days past due, else 0 = safe/approved), cleans
and encodes the features, trains Logistic Regression / Random Forest /
XGBoost, prints an accuracy comparison and classification report, and
saves the best model to `models/card_model.joblib`.

## 4. Run the web app

```bash
python app.py
```

Open `http://127.0.0.1:5000` in your browser, fill out the form, and
submit to get an APPROVED / REJECTED result.

## Project structure

⚙️ Features
Automated Credit Card Approval Prediction
Data Preprocessing and Cleaning
Machine Learning Model Training
Real-Time Prediction using Flask
User-Friendly Web Interface
Faster and Consistent Decision Making

🔄 Workflow
Collect Applicant Data
Preprocess Dataset
Train Machine Learning Model
Save Trained Model
Deploy Using Flask
Predict Approval Status
Display Result to User

📊 Machine Learning Algorithms
The project can utilize:

Logistic Regression
Decision Tree
Random Forest
Gradient Boosting / XGBoost
The best-performing model is saved and used for prediction.

🎯 Expected Outcomes
Reduced manual effort in credit approval.
Faster processing of applications.
Improved decision-making accuracy.
Better customer satisfaction.
Consistent and unbiased approval decisions.

🔮 Future Enhancements
Integration with live banking databases.
Credit score API integration.
Cloud deployment.
Explainable AI for decision transparency.
Mobile application support.

## Why `encoding_maps.py` exists

The original handbook has the web form send integers (e.g. gender,
education level) straight to the model, but never shows how those
integers are assigned during training. If the training script and the
HTML dropdowns disagree on what code `2` means for "education," every
prediction is silently wrong. `encoding_maps.py` is the single source of
truth both `train.py` and `templates/index.html` are built from — if you
ever add or reorder a category, update both from this file.

## Notes / caveats

- This is a teaching project, not a real underwriting system. The label
  ("60+ days past due at any point") is one reasonable definition among
  several the original dataset supports — treat accuracy numbers as
  illustrative, not production-grade.
- `train.py` drops any row whose category isn't in `encoding_maps.py` to
  keep the training data and the web form in sync. Check the printed
  "dropped N rows" message to see how many that affected.
- Next steps suggested by the handbook (hyperparameter tuning with
  `GridSearchCV`, feature-importance plots, Docker + cloud deployment)
  aren't implemented here — the code above only covers what's needed to
  train and serve the model locally.

👨‍💻 Author
SYED MOHAMMAD KHAJA

Project: Credit Card Approval Prediction

📜 License
This project is developed for educational and academic purposes.
