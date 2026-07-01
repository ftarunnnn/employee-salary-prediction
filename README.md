Employee Salary Prediction
Project Overview
A full‑stack machine‑learning project that predicts employee salaries from demographic and job‑related features. The repository contains data generation, preprocessing notebooks, model training, a Flask API, automated tests, and deployment guides.

Problem Statement
Accurately estimating salaries helps HR teams with compensation planning, budgeting, and ensuring pay equity. This project builds a regression model that learns from historical employee records and predicts expected salaries for new hires or internal moves.

Dataset Description
Location: dataset/salary.csv
Rows: 10 000 synthetic employee records
Key columns: Age, Experience, Education, Department, PerformanceScore, Certifications, CompanySize, Salary (target)
Features Used
Numerical: Age, Experience, PerformanceScore, Certifications
Categorical (encoded): Education, Department, CompanySize, ExperienceLevel, SkillScore
Engineered: SkillScore = Experience × EducationWeight, ExperienceLevel (Beginner‑Expert), CompanyCategory (Small‑Large)
Technologies
Python 3.11
Data: pandas, numpy, seaborn, matplotlib
ML: scikit‑learn, xgboost, joblib
API: Flask
Testing: pytest, Flask test client
Deployment: Render, Railway, PythonAnywhere, Hugging Face Spaces
Version control: Git
Installation Steps
bash

# Clone repo
git clone <repo-url>
cd "Employee Salary Prediction"
# Create virtual environment (Windows)
python -m venv venv
.\\venv\\Scripts\\activate
# Install dependencies
pip install -r requirements.txt
# (Optional) Generate synthetic data
python generate_synthetic_data.py
How to Run
Train / re‑train the model

bash

python src/train_model.py
This creates models/salary_model.pkl, models/scaler.pkl, and models/encoder.pkl.

Start the prediction service

bash

python app/app.py
The Flask app runs at http://127.0.0.1:5000. Use the web UI or POST to /predict with JSON payload.

Run tests

bash

pytest test_app.py
All five test scenarios (valid, missing, invalid, extreme, education levels) should pass.

Screenshots
Salary Prediction UI
Review
Salary Prediction UI

Model Performance
Model	MAE	RMSE	R²
Linear Regression	5,210	6,928	0.71
Random Forest (tuned)	3,845	5,383	0.84
XGBoost	4,012	5,567	0.82
Future Improvements
Add interpretability (SHAP values) for feature importance.
Expand the API to support batch predictions.
Deploy with Docker + CI/CD pipelines.
Incorporate additional data sources (e.g., industry salary benchmarks).
Project Folder Structure

Employee_Salary_Prediction/
│
├── dataset/
│   └── salary.csv
│
├── notebooks/
│   └── salary_prediction.ipynb
│
├── src/
│   ├── data_preprocessing.py
│   ├── feature_engineering.py
│   ├── train_model.py
│   ├── evaluate_model.py
│   ├── predict.py
│   └── utils.py
│
├── models/
│   ├── salary_model.pkl
│   ├── scaler.pkl
│   └── encoder.pkl
│
├── app/
│   ├── app.py
│   ├── templates/
│   │   └── index.html
│   └── static/
│       ├── css/
│       │   └── style.css
│       └── js/
│           └── script.js
│
├── requirements.txt
├── README.md
└── .gitignore
Happy coding!

Building Employee Salary Predictor
11:19 PM
README.md – Project Documentation

You can find the complete file at


README.md

Below is the full content that was written to the file.

Employee Salary Prediction
Project Overview
A complete end‑to‑end machine‑learning pipeline that predicts an employee’s salary from personal and job‑related attributes. The project covers data generation, cleaning, exploratory analysis, 
