# 💳 Credit Card Fraud Detection Using Machine Learning

---

# 📌 Project Overview

Credit card fraud is one of the most significant challenges faced by financial institutions today. With millions of transactions occurring daily, identifying fraudulent transactions quickly and accurately is crucial for minimizing financial losses and protecting customers.

This project develops a **Machine Learning-based Fraud Detection System** using the **Random Forest Classifier** to distinguish between legitimate and fraudulent credit card transactions. The project involves data preprocessing, exploratory data analysis (EDA), correlation analysis, model training, and performance evaluation.

---

# 🎯 Objectives

* Detect fraudulent credit card transactions using machine learning.
* Analyze transaction patterns and class imbalance.
* Perform exploratory data analysis (EDA).
* Visualize relationships between transaction features.
* Train a Random Forest Classification model.
* Evaluate model performance using multiple classification metrics.

---

# 📊 Dataset Information

The dataset contains anonymized credit card transactions made by European cardholders.

### Features

| Feature  | Description                                      |
| -------- | ------------------------------------------------ |
| Time     | Seconds elapsed between transactions             |
| V1 - V28 | Principal Components obtained through PCA        |
| Amount   | Transaction amount                               |
| Class    | Target Variable (0 = Legitimate, 1 = Fraudulent) |

### Target Variable

| Class | Meaning                |
| ----- | ---------------------- |
| 0     | Valid Transaction      |
| 1     | Fraudulent Transaction |

---

# ⚠️ Problem Statement

Fraudulent transactions represent only a very small fraction of the total transactions, creating a highly imbalanced classification problem.

Challenges include:

* Severe class imbalance
* High dimensionality
* Need for accurate fraud detection
* Minimizing false positives and false negatives

---

# 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Jupyter Notebook

---

# 🔄 Project Workflow

## 1️⃣ Data Collection

The credit card transaction dataset is loaded using Pandas.

```python
data = pd.read_csv("creditcard.csv")
```

---

## 2️⃣ Exploratory Data Analysis (EDA)

Performed the following analysis:

* Dataset inspection
* Statistical summary
* Fraud vs Non-Fraud comparison
* Transaction amount analysis
* Correlation analysis

### Key Observation

The dataset is highly imbalanced:

```text
Fraud Transactions << Valid Transactions
```

This imbalance makes fraud detection a challenging classification problem.

---

## 3️⃣ Correlation Analysis

A correlation matrix was generated to understand feature relationships.

```python
corrmat = data.corr()
sns.heatmap(corrmat)
```

### Purpose

* Identify feature dependencies
* Understand variable relationships
* Support feature analysis

---

## 4️⃣ Data Preparation

Features and target variable were separated.

```python
X = data.drop("Class", axis=1)
Y = data["Class"]
```

### Train-Test Split

```python
train_test_split(
    X,
    Y,
    test_size=0.2,
    random_state=42
)
```

Dataset split:

* Training Data → 80%
* Testing Data → 20%

---

## 5️⃣ Model Development

### Random Forest Classifier

The Random Forest algorithm was used because it:

* Handles large datasets effectively
* Reduces overfitting
* Works well with imbalanced datasets
* Provides strong classification performance

```python
from sklearn.ensemble import RandomForestClassifier

rfc = RandomForestClassifier()
rfc.fit(xTrain, yTrain)
```

---

## 6️⃣ Prediction

The trained model predicts whether a transaction is:

* Legitimate
* Fraudulent

```python
yPred = rfc.predict(xTest)
```

---

# 📈 Model Evaluation

The model was evaluated using multiple performance metrics.

### Accuracy

Measures overall correctness.

```text
Accuracy = (TP + TN) / Total Predictions
```

### Precision

Measures how many predicted fraud transactions were actually fraud.

```text
Precision = TP / (TP + FP)
```

### Recall

Measures the model's ability to detect actual fraud cases.

```text
Recall = TP / (TP + FN)
```

### F1 Score

Balances Precision and Recall.

### Matthews Correlation Coefficient (MCC)

Provides a balanced measure even when classes are highly imbalanced.

---

# 📊 Visualizations

The project includes:

* Fraud vs Valid Transaction Analysis
* Transaction Amount Distribution
* Correlation Heatmap
* Statistical Summary Visualizations

---

# 📁 Project Structure

```text
Credit-Card-Fraud-Detection/
│
├── creditcard.csv
├── Credit_card_fraud_detection.ipynb
├── README.md
└── requirements.txt
```

---

# 🚀 Installation

### Clone Repository

```bash
git clone https://github.com/yourusername/Credit-Card-Fraud-Detection.git
```

### Move to Project Directory

```bash
cd Credit-Card-Fraud-Detection
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Launch Notebook

```bash
jupyter notebook
```

---

# 📦 Requirements

```text
numpy
pandas
matplotlib
seaborn
scikit-learn
jupyter
```

---

# 📌 Key Insights

✅ Fraudulent transactions represent only a tiny percentage of all transactions.

✅ The dataset is highly imbalanced.

✅ Random Forest performs effectively for fraud detection.

✅ Multiple evaluation metrics are necessary to assess model performance accurately.

✅ Fraud detection systems can significantly reduce financial losses for institutions.

---

# 🔮 Future Improvements

* Hyperparameter Tuning
* Cross Validation
* SMOTE for Class Balancing
* XGBoost Classifier
* LightGBM Classifier
* Deep Learning Approaches
* Real-Time Fraud Detection System
* Deployment using Flask or Streamlit

---

# 🎓 Learning Outcomes

Through this project, I gained practical experience in:

* Data Cleaning
* Exploratory Data Analysis
* Feature Engineering
* Machine Learning Classification
* Fraud Analytics
* Model Evaluation
* Financial Data Analysis
* Python Programming

---

# 👩‍💻 Author

**Zaid Arif Saifan**

🎓 Masters in Financial Engineering
🏫 HEC Montreal, Canada

### Skills Demonstrated

* Machine Learning
* Data Analysis
* Fraud Detection
* Python
* Pandas
* Scikit-Learn
* Data Visualization

---

⭐ If you found this project useful, consider giving it a star on GitHub!
