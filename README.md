# Fraud-Detection-Project-Insurance-Claims-Dataiku-DSS
# 🚨 Fraud Detection Project – Insurance Claims (Dataiku DSS)

## 🧠 Goal
Build a binary classification model to predict if a customer is likely to commit fraud based on historical insurance data, customer profiles, contracts, and location data.

---

## 📁 Data Sources

| File                  | Description                                |
|-----------------------|--------------------------------------------|
| `Contracts.xlsx`      | Insurance contract data                    |
| `Customers.xlsx`      | Customer demographic & profile info        |
| `Historical_Claims.xlsx` | Past claims history, including fraud labels |
| `Departements.xlsx`   | Geographic data (regions, departments)     |

---

## 🧱 Workflow Overview (Dataiku)

### 1.  **Data Joining**
- Join `Contracts` with `Customers`
- Add `Historical_Claims` (to create the target variable)
- Enrich with `Departements` to include geographic context

### 2. **Data Preparation**
- Clean & normalize numerical features
- Encode categorical variables with dummy encoding
- Reject IDs and irrelevant features (e.g., litigation_flag)

### 3.  **Target Variable**
- A new binary column `is_fraud` is created:
  - 1 → Fraudulent customer
  - 0 → Non-fraudulent

### 4.  **Train / Test Split**
- Dataset split into `Train_Data` and `Test_Data` (80/20)
- Random sampling used for unbiased split

### 5. ⚖**Oversampling**
- SMOTE technique applied on the training set (`Train_Data`) to balance fraud vs. non-fraud cases (50/50)

### 6.  **Machine Learning**
- Algorithms used:
  - Random Forest 🌲
  - Logistic Regression 📊
  - Gradient Boosting 📈
  - Support Vector Machine (SVM) 💡

- Feature handling:
  - Avg-std rescaling for numerical variables
  - Dummy encoding for categorical variables

### 7. **Model Evaluation**
- Evaluation metrics:
  - AUC ROC
  - Precision, Recall
  - Confusion matrix
- Best model selected based on balance between performance and interpretability

---

##  Outputs

| Output Dataset       | Description                         |
|----------------------|-------------------------------------|
| `Oversampling_Data`  | Balanced dataset used for modeling  |
| `Test_Data`          | Held-out test data (untouched)      |
| `Predict fraud (binary)` | Visual analysis + trained models |

---

##  Next Steps
- Deploy the best model for scoring in production
- Set up automatic retraining with updated claims data
- Build dashboard for live fraud monitoring

---

##  Author
Hoda – Junior Data Scientist  
Project built on **Dataiku DSS**  
