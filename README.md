readme_content = """
# 📞 TELECOM CUSTOMER CHURN PREDICTION

## 🏆 OVERVIEW

This project aims to predict **customer churn** for a leading telecom operator using machine learning. The objective is to empower customer retention teams with insights and risk scores that help prioritize outreach and reduce revenue loss.

---

## 📂 DATASET

### 📊 Attributes:
- `State` – Customer location
- `Account Length` – Duration of the customer’s subscription
- `Area Code` – Regional identifier
- `International Plan` – Whether international calls are enabled
- `VMail Plan` – Voice mail subscription
- `Day/Eve/Night/Intl Mins/Calls/Charge` – Usage metrics
- `CustServ Calls` – Number of customer service interactions
- `Churn` – 🔺 Target variable (Yes = customer churned)

---

## 📌 BUSINESS OBJECTIVES

1. Predict whether a customer will **churn** or **stay**
2. Identify key drivers of churn
3. Generate **churn risk scores** to guide customer care prioritization

---

## ⚙️ PREPROCESSING TECHNIQUES

- 🔹 Handled missing values
- 🔹 Label encoding of categorical variables
- 🔹 Outlier treatment using IQR and median imputation
- 🔹 Normalization using `MinMaxScaler` and `StandardScaler`
- 🔹 Feature selection based on importance
- 🔹 Train-test split using stratified sampling

---

## ⚠️ CLASS IMBALANCE

Since only ~14% of customers churn, the dataset is imbalanced. This was addressed via:

- 🔸 **Under-sampling**
- 🔸 **Over-sampling (SMOTE)**
- 🔸 **Class weights**

---

## ⚡ MODEL PERFORMANCE COMPARISON

| Model Type                 | Model Name       | Accuracy | F1 Score |
|---------------------------|------------------|----------|----------|
| ✅ **Best Overall**        | Random Forest     | **96.71%** | **96.51%** |
| 🟡 Under-sampling Model    | Bagging Tree      | 92.81%   | 93.15%   |
| 🔵 SMOTE (Over-sampling)   | XGBoost           | 95.76%   | 95.59%   |
| 🔹 Baseline Model          | Logistic Regression | 88%    | 68%      |

---

## ✅ FINAL RECOMMENDATION:

1. **Best Overall Model:**  
   **Random Forest**  
   *Accuracy: 96.71% | F1 Score: 96.51%*  
   **Reason:** Achieves the highest accuracy and balanced performance across churn and non-churn classes.

2. **Best Model with Under-Sampling:**  
   **Bagging Tree**  
   *Accuracy: 92.81% | F1 Score: 93.15%*  
   **Reason:** Performs well even after handling imbalance through under-sampling.

3. **Best Model with SMOTE Over-Sampling:**  
   **XGBoost**  
   *Accuracy: 95.76% | F1 Score: 95.59%*  
   **Reason:** Handles class imbalance effectively and achieves very high prediction scores.

---

## 📊 CHURN RISK SCORE INSIGHTS

1. High churn risk customers (score ~1.0) require **urgent retention** measures.
2. Moderate risk customers (score 0.53–0.63) are fewer and can be managed with **targeted but less intensive** strategies.
3. Resource allocation should focus on **high-risk** first to maximize retention ROI.

---

## 📊 EVALUATION METRICS

- **Accuracy** – Overall correct predictions
- **F1-Score** – Balanced score between precision & recall
- **ROC-AUC** – Ability to distinguish between churned & non-churned customers

---

## 📌 KEY INSIGHTS

- Customers with **International Plans** and frequent **Customer Service Calls** are more likely to churn.
- Random Forest and XGBoost deliver the most robust and generalizable predictions.
- Churn risk scoring can guide **retention resource allocation** effectively.

---

## 🛠 INSTALLATION

```bash
pip install numpy pandas scikit-learn xgboost seaborn matplotlib imbalanced-learn
