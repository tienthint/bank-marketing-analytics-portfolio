# Bank Marketing Analytics — Predictive Modeling

This project analyzes a real-world dataset from a Portuguese bank's term deposit marketing campaign. The goal is to build a predictive model to identify customers most likely to subscribe to a term deposit, using demographic, financial, and campaign-related features.

---

## Objective

Predict which customers are most likely to respond positively to a term deposit marketing campaign, and provide business insights to guide targeting strategy.

---

## Tools Used

- Python (Pandas, Scikit-learn, Seaborn, Matplotlib)
- Logistic Regression & Random Forest
- Jupyter Notebooks in VSCode
- GitHub for version control

---

## 📊 Project 1: Predictive Modeling Summary

### 🔍 Approach

- Performed data cleaning and exploratory data analysis (EDA)
- Handled categorical variables using one-hot encoding
- Standardized numerical features
- Built and evaluated two models: Logistic Regression and Random Forest

---

### 📈 Model Performance

| Metric          | Logistic Regression | Random Forest |
|-----------------|---------------------|----------------|
| Precision (1)   | 0.64                | 0.67           |
| Recall (1)      | 0.34                | 0.40           |
| F1-score (1)    | 0.45                | 0.50           |
| ROC-AUC Score   | **0.91** ✅         | **0.93** ✅    |

> Note: Class imbalance was present (only ~11.7% subscribed), so we focused on recall and ROC-AUC instead of accuracy.

---

### 🔑 Key Insights from Modeling

- **Most predictive features**:
  - `duration` of last contact (note: not usable for targeting)
  - `balance`, `age`, `campaign`, and `previous outcome (poutcome)`
- Customers with `poutcome = success` have a **64.7% chance** of subscribing — the most influential actionable variable.
- Contacting customers via **cellular** results in significantly higher success than `telephone` or `unknown`.
- Education, job type, and campaign frequency also show clear effects on conversion likelihood.


---

## Project Porfolio

Project 1: Predictive Modeling — Complete  
Project 2: Customer Segmentation + Power BI  
Project 3: Campaign Effectiveness Analysis  
Project 4: Attribution Modeling + Portfolio Polishing  

---

## 📫 Author

**Thi Nguyen**  
Marketing Analytics | Data Science | Python | Power BI  
Feel free to connect: [LinkedIn](https://www.linkedin.com/in/tienthinguyen)

