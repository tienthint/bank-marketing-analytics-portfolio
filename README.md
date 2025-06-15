# Bank Marketing Analytics — Predictive Modeling

This project analyzes a real-world dataset from a Portuguese bank's term deposit marketing campaign. The goal is to build a predictive model to identify customers most likely to subscribe to a term deposit, using demographic, financial, and campaign-related features.

## Project Porfolio

Project 1: Predictive Modeling — Complete  
Project 2: Customer Segmentation + Power BI  
Project 3: Campaign Effectiveness Analysis  
Project 4: Attribution Modeling + Portfolio Polishing  

---



---

## Project 1: Predictive Modeling Summary

## Objective

Predict which customers are most likely to respond positively to a term deposit marketing campaign, and provide business insights to guide targeting strategy.

---

## Tools Used

- Python (Pandas, Scikit-learn, Seaborn, Matplotlib)
- Logistic Regression & Random Forest
- Jupyter Notebooks in VSCode
- GitHub for version control

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
| ROC-AUC Score   | **0.91**            | **0.93**       |

> Note: Class imbalance was present (only ~11.7% subscribed), so we focused on recall and ROC-AUC instead of accuracy.

---

### Key Insights from Modeling

- **Most predictive features**:
  - `duration` of last contact (note: not usable for targeting)
  - `balance`, `age`, `campaign`, and `previous outcome (poutcome)`
- Customers with `poutcome = success` have a **64.7% chance** of subscribing — the most influential actionable variable.
- Contacting customers via **cellular** results in significantly higher success than `telephone` or `unknown`.
- Education, job type, and campaign frequency also show clear effects on conversion likelihood.

---

## Project 2: Customer Segmentation & Dashboard

In this project, we use unsupervised machine learning to segment banking customers into distinct groups based on their demographic and financial attributes. The goal is to help marketers tailor campaign strategies for each segment.

### Objective
- Identify meaningful customer segments
- Profile each group (e.g., age, balance, housing/loan status)
- Export data for Power BI dashboarding

### Dataset
- **Source**: [UCI Bank Marketing Dataset](https://archive.ics.uci.edu/ml/datasets/bank+marketing)
- **Features Used**:
  - `age`, `job`, `marital`, `education`, `default`, `balance`, `housing`, `loan`

### Techniques Used
- One-hot encoding for categorical variables
- Standardization with `StandardScaler`
- Clustering using **KMeans**
- Elbow method for optimal cluster selection
- Cluster profiling with group statistics

### Result
- Selected **k=4** clusters based on elbow curve
- Each cluster shows distinct behavioral and financial traits
- Conversion rates (`y`) vary significantly across clusters, enabling targeted marketing

### Output
- `data/customer_clustered.csv`: clustered dataset for Power BI
- `notebooks/2_customer_segmentation.ipynb`: full code and insights
- ROC curve and classification metrics from Week 1 used for campaign effectiveness comparison


---
## Project 3: Campaign Effectiveness Summary

### Funnel Overview

The marketing campaign was evaluated using a 3-stage funnel:

| Stage              | Count     |
|--------------------|-----------|
| Total Customers    | 45,211    |
| Contacted          | 45,211    |
| Converted          | 5,289     |
| **Conversion Rate** | **11.7%** |

> All customers in the dataset received at least one contact attempt.

---

### Hypothesis Testing

We performed statistical tests to validate whether certain features significantly influence customer conversion.

| Hypothesis | Test Type | P-Value | Conclusion |
|------------|-----------|---------|------------|
| Education level affects subscription | Chi-Square | ~`1.63e-51` | ✅ Significant |
| Previous outcome affects current conversion | Chi-Square | ~`0.00` | ✅ Significant |
| Call duration impacts conversion | T-Test | ~`0.00` | ✅ Significant |

All tested features show a statistically significant relationship with campaign success.

---

### Key Insights

- **Education**: Higher education correlates with increased conversion
- **Poutcome = success**: Strongest predictor of conversion (>65%)
- **Call duration**: Longer conversations positively influence outcomes

These findings can guide segmentation, call strategy, and retargeting in future campaigns.

## Author

**Thi Nguyen**  
Marketing Analytics | Data Science | Python | Power BI  
Feel free to connect: [LinkedIn](https://www.linkedin.com/in/tienthinguyen)

