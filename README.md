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
# Project 3: Marketing Channel Attribution & Contact Strategy Optimization

This project analyzes the effectiveness of different marketing outreach strategies from a bank campaign dataset. The goal is to identify which contact methods, outreach frequencies, and previous outcomes contribute to customer conversion, to inform future marketing investments.

---

## Dataset

- **Source**: UCI Bank Marketing Dataset
- **Records**: 45,211
- **Target Variable**: `y` – whether the customer subscribed to a term deposit (`yes` / `no`)
- **Key Features Used**:
  - `contact`: Marketing contact communication type (cellular, telephone, unknown)
  - `month`: Last contact month of year
  - `campaign`: Number of contacts during the current campaign
  - `poutcome`: Outcome of the previous marketing campaign
  - `y`: Target response

---

## Key Analyses

### Conversion by Contact Method
| Contact Method | Conversion Rate |
|----------------|-----------------|
| Cellular       | 14.9%           |
| Telephone      | 13.4%           |
| Unknown        | 4.1%            |

> **Cellular** is the most effective contact channel.

---

### Conversion by Month
| Best Months | Conversion Rate |
|-------------|-----------------|
| March       | 51.9%           |
| October     | 43.8%           |
| September   | 46.5%           |

> **May**, despite high volume, had the lowest conversion (6.7%).

---

### Conversion by Campaign Frequency
| Contact Attempts | Conversion Rate |
|------------------|-----------------|
| 1                | 14.6%           |
| 2                | 11.2%           |
| >5               | ~2% or lower    |

> High-frequency contact may lead to **diminishing returns**.

---

###  Previous Campaign Outcome
| Outcome   | Conversion Rate |
|-----------|-----------------|
| Success   | 64.7%           |
| Failure   | 12.6%           |
| Unknown   | 9.2%            |

> Customers who previously converted are more likely to convert again.


---

## Insights & Recommendations

- Use **cellular contact** as the primary outreach channel.
- Focus marketing efforts in **March, September, and October**.
- Limit contact attempts to **1–2 times per customer**.
- Prioritize follow-ups with customers who previously said **"yes"**.

## Author

**Thi Nguyen**  
Marketing Analytics | Data Science | Python | Power BI  
Feel free to connect: [LinkedIn](https://www.linkedin.com/in/tienthinguyen)

