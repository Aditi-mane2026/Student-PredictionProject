# Student Performance Prediction

An end-to-end machine learning web application that predicts a student's **math score** based on demographic and academic factors.

## Demo

Fill in the student details on the prediction form and get an instant math score prediction.

## Features

- Predicts math score based on:
  - Gender
  - Race/Ethnicity
  - Parental level of education
  - Lunch type
  - Test preparation course
  - Reading score
  - Writing score
- Flask web interface with a prediction form
- Trained on real student performance data
- Deployed on AWS Elastic Beanstalk with CI/CD via GitHub Actions

## Tech Stack

- **Language:** Python 3.10
- **Web Framework:** Flask
- **ML Libraries:** scikit-learn, XGBoost, CatBoost
- **Data:** Pandas, NumPy
- **Deployment:** AWS Elastic Beanstalk, GitHub Actions

## Models Compared

The training pipeline evaluates 7 models and picks the best by R² score:

| Model | Tuned |
|---|---|
| Linear Regression | - |
| Decision Tree | Yes |
| Random Forest | Yes |
| Gradient Boosting | Yes |
| XGBoost | Yes |
| CatBoost | Yes |
| AdaBoost | Yes |

## Project Structure

```
├── app.py                          # Flask application
├── src/
│   ├── components/
│   │   ├── data_ingestion.py       # Load and split data
│   │   ├── data_transformation.py  # Preprocessing pipeline
│   │   └── model_trainer.py        # Train and select best model
│   ├── pipeline/
│   │   ├── predict_pipeline.py     # Inference pipeline
│   │   └── train_pipeline.py       # Training pipeline
│   ├── exception.py
│   ├── logger.py
│   └── utils.py
├── artifacts/                      # Saved model and preprocessor
├── notebook/                       # EDA and model training notebooks
├── templates/                      # HTML templates
└── requirements.txt
```

## Setup & Run Locally

```bash
# Clone the repo
git clone https://github.com/Aditi-mane2026/Student-PredictionProject.git
cd Student-PredictionProject

# Install dependencies
pip install -r requirements.txt

# Run the app
python app.py
```

Then open **http://localhost:5000/predictdata** in your browser.
