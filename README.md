# Customer Churn Prediction - DS-2 Hackathon

This project predicts whether a telecom customer is likely to churn based on their service usage patterns and demographics. It’s designed for the **DS-2: Stop the Churn Hackathon**, and includes preprocessing, training multiple models, generating predictions, and visualizing insights.

---

## Repository Structure
```
├── telco_train.csv           # Training data
├── telco_test.csv            # Test data (without labels)
├── predictions.csv           # Final predicted churn probabilities
├── model.pkl                 # Trained Logistic Regression model
├── scaler.pkl                # Scaler for numeric features
├── label_encoders.pkl        # Encoders for categorical features
├── churn_train.ipynb         # Full training pipeline
├── churn_test.ipynb          # Prediction
├── churn_visualization,ipynb # visualization
└── README.md                 # This file
```

---

## Project Overview

Churn prediction is crucial for telecom providers to retain their most valuable customers. This project uses customer data to:

- Train classification models (Logistic Regression, Random Forest, XGBoost)
- Optimize based on AUC-ROC score
- Predict churn probability for test samples
- Visualize risk distribution and top at-risk customers

---

## How to Run This Project Locally

### Clone the Repository & install required libraries

```bash
git clone https://github.com/Somen04/Stop-the-Churn-Predictor.git
cd Stop-the-Churn-Predictor
pip install pandas numpy scikit-learn xgboost matplotlib seaborn joblib
```
---

### Prediction Approach

This project uses a structured machine learning pipeline to predict customer churn:

- **Data Preprocessing:**
  - Dropped irrelevant columns (e.g., `customerID`)
  - Converted `TotalCharges` to numeric format with error handling
  - Handled missing values in both numerical and categorical columns
  - Applied `LabelEncoder` to convert categorical columns to numerical
  - Scaled numeric features using `StandardScaler`

- **Model Training:**
  - Trained and evaluated three models:
    - Logistic Regression
    - Random Forest Classifier
    - XGBoost Classifier
  - Split the dataset into training and validation sets (80/20)
  - Optimized model performance based on **AUC-ROC score**

- **Model Evaluation:**
  - Logistic Regression: AUC ≈ 0.8613
  - Random Forest: AUC ≈ 0.8364
  - XGBoost: AUC ≈ 0.8361
  - Logistic Regression selected as best model due to higher AUC

- **Prediction:**
  - Applied trained model to the `telco_test.csv` dataset
  - Encoded and scaled test data using saved encoders and scaler
  - Generated churn probabilities for each customer

- **Output:**
  - Saved predictions as `predictions.csv` containing:
    - `CustomerID`
    - `Churn_Probability`

- **Model Interpretability:**
  - Visualized feature importance using Logistic Regression coefficients
  
##  Video Presentation

Watch the full demo and explanation here:

👉 [Watch on YouTube](https://youtu.be/_c9O3tzNFQ4?si=koOqyPo6JGXlnA54)

## Author

- [Somen Senapati](https://github.com/Somen04)

