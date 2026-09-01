# Customer Churn Prediction using Machine Learning

A machine learning project that predicts customer churn in a telecom company using various classification algorithms. This project demonstrates data preprocessing, exploratory data analysis (EDA), feature engineering, and model building with multiple algorithms.

## 📋 Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Features](#features)
- [Technologies & Libraries](#technologies--libraries)
- [Installation](#installation)
- [Usage](#usage)
- [Data Preprocessing](#data-preprocessing)
- [Models](#models)
- [Results](#results)
- [Key Findings](#key-findings)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

Customer churn is a critical business metric that represents the percentage of customers who leave a service provider within a specific time period. This project builds a predictive model to identify customers likely to churn, allowing businesses to take proactive retention measures.

**Objective**: Develop a machine learning model that accurately predicts whether a customer will churn or continue with the telecom service.

## 📊 Dataset

**Source**: WA_Fn-UseC_-Telco-Customer-Churn.csv

**Dataset Statistics**:
- **Total Records**: 7,043 customers
- **Total Features**: 21 columns
- **Target Variable**: Churn (Yes/No)

### Features Overview

| Category | Features |
|----------|----------|
| **Demographic** | Gender, Age (SeniorCitizen), Partner, Dependents |
| **Services** | PhoneService, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies |
| **Account** | Tenure, Contract, PaperlessBilling, PaymentMethod |
| **Billing** | MonthlyCharges, TotalCharges |

### Data Types
- **Numeric**: SeniorCitizen, tenure, MonthlyCharges
- **Categorical**: gender, Partner, Dependents, PhoneService, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies, Contract, PaperlessBilling, PaymentMethod, Churn

## 🗂️ Project Structure

```
Customer_Churn_Prediction/
├── Customer_Churn_Prediction_using_ML.ipynb
├── WA_Fn-UseC_-Telco-Customer-Churn.csv
├── README.md
└── models/
    └── (saved model files)
```

## ✨ Features

- **Comprehensive Data Preprocessing**: Handling missing values, data type conversion, and encoding
- **Exploratory Data Analysis (EDA)**: Visualization and statistical analysis of features
- **Class Imbalance Handling**: Using SMOTE (Synthetic Minority Over-sampling Technique)
- **Multiple ML Algorithms**:
  - Decision Tree Classifier
  - Random Forest Classifier
  - XGBoost Classifier
- **Model Evaluation**: Accuracy, Confusion Matrix, Classification Report
- **Cross-Validation**: Using k-fold cross-validation for robust model assessment

## 🛠️ Technologies & Libraries

```python
# Data Processing & Analysis
pandas
numpy

# Visualization
matplotlib
seaborn

# Machine Learning
scikit-learn
imbalanced-learn (SMOTE)
xgboost

# Model Persistence
pickle
```

## 📦 Installation

### Requirements
- Python 3.7 or higher
- Jupyter Notebook or Google Colab

### Setup Instructions

1. **Clone the repository**:
```bash
git clone https://github.com/aryansinghvit/Customer_Churn_Prediction.git
cd Customer_Churn_Prediction
```

2. **Install required libraries**:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn imbalanced-learn xgboost
```

3. **For Google Colab** (as the project was developed there):
```python
# All required libraries are pre-installed
# Just upload the CSV file or mount Google Drive
from google.colab import drive
drive.mount('/content/drive')
```

## 🚀 Usage

### Running the Notebook

1. Open `Customer_Churn_Prediction_using_ML.ipynb`
2. Ensure the dataset file is in the same directory or update the path
3. Run cells sequentially from top to bottom

### Basic Workflow

```python
import pandas as pd
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder
from imblearn.over_sampling import SMOTE

# Load data
df = pd.read_csv("WA_Fn-UseC_-Telco-Customer-Churn.csv")

# Data preprocessing
df = df.drop(columns=["customerID"])

# Feature encoding and model training
# (See notebook for complete implementation)
```

## 🔧 Data Preprocessing

### Steps Implemented

1. **Data Cleaning**:
   - Removed non-essential columns (customerID)
   - Checked for missing values
   - Validated data types

2. **Encoding**:
   - Label Encoding for categorical variables
   - Conversion of target variable (Churn: Yes/No → 1/0)

3. **Feature Scaling**:
   - Standardization of numerical features
   - Preparation for model training

4. **Class Imbalance Handling**:
   - Applied SMOTE to balance the dataset
   - Prevents model bias towards majority class

## 🤖 Models

### 1. Decision Tree Classifier
- **Pros**: Interpretable, handles non-linear relationships
- **Cons**: Prone to overfitting
- **Use Case**: Baseline model, feature importance analysis

### 2. Random Forest Classifier
- **Pros**: Robust, handles non-linear relationships, provides feature importance
- **Cons**: Less interpretable
- **Use Case**: Balanced accuracy and interpretability

### 3. XGBoost Classifier
- **Pros**: Highest accuracy, handles imbalanced data well, fast training
- **Cons**: Complex tuning, black-box nature
- **Use Case**: Best performance for churn prediction

## 📈 Results

The notebook includes:

- **Confusion Matrices**: Visualization of True/False Positives and Negatives
- **Classification Reports**: Precision, Recall, F1-Score for both classes
- **Accuracy Scores**: Comparison across models
- **Cross-Validation Scores**: K-fold validation results

### Expected Performance Range
- **Accuracy**: 75-85% (depending on model and validation approach)
- **Precision**: 65-80% (correctly identified churners)
- **Recall**: 50-70% (capturing actual churners)

## 🔍 Key Findings

Based on typical churn analysis:

1. **Tenure Impact**: Customers with lower tenure are more likely to churn
2. **Contract Type**: Month-to-month contracts have higher churn rates
3. **Internet Service**: Fiber optic users show higher churn tendency
4. **Services**: Customers with fewer additional services churn more
5. **Tech Support**: Tech support adoption correlates with customer retention

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit changes (`git commit -am 'Add improvement'`)
4. Push to branch (`git push origin feature/improvement`)
5. Open a Pull Request

## 📝 License

This project is open source and available under the MIT License. See the LICENSE file for details.

## 📧 Contact

**Author**: Aryan Singh  
**GitHub**: [@aryansinghvit](https://github.com/aryansinghvit)  
**Project Repository**: [Customer_Churn_Prediction](https://github.com/aryansinghvit/Customer_Churn_Prediction)

## 📚 References

- [Scikit-learn Documentation](https://scikit-learn.org/)
- [XGBoost Documentation](https://xgboost.readthedocs.io/)
- [SMOTE Documentation](https://imbalanced-learn.org/stable/references/generated/imblearn.over_sampling.SMOTE.html)
- [Churn Analysis Best Practices](https://en.wikipedia.org/wiki/Customer_retention)

## 🙏 Acknowledgments

- Telecom dataset from Kaggle/UCI Machine Learning Repository
- Open source community for excellent ML libraries
- Google Colab for computation support

---

**Last Updated**: September 2026  
**Status**: ✅ Active & Maintained
