# 📊 OTT Subscription Churn Analytics & Customer Intelligence

An end-to-end data analytics and customer intelligence pipeline built to analyze subscriber churn, quantify revenue loss, and identify high-risk cohorts across subscription tiers, customer demographics, and support interactions.

---

## 📌 Executive Summary

* **Overall Churn Rate**: **28.6%** (Retention Rate: 71.4%)
* **Contract Risk Disparity**: Monthly contract subscribers churn at **55.6%**, compared to just **8.3%** for annual subscribers (a ~6.7x risk multiplier).
* **Financial Impact**: Identified **$74/mo in direct MRR leakage** and **$2,047 in total CLTV loss**, representing an **18% total revenue loss**.
* **Geographic & Temporal Trends**: Churn spiked sharply in **September 2024**, with **Karnataka** experiencing the highest concentration of churned accounts.

---

## 🛠️ Architecture & Tech Stack
* **Core Language**: Python (Pandas, NumPy)
* **Database & Querying**: SQLite via `sqlite3` and Pandas SQL integrations
* **Data Visualization**: Matplotlib & Seaborn
* **Environment**: Jupyter Notebook

---

## 🗄️ Relational Data Model

The pipeline extracts and joins relational tables from the `customer_churn` database:

1. **`db_customer`**: `customerid`, `name`, `country`, `state`, `gender`, `dob`, `interests`, `pincode`
2. **`db_subscription`**: `customerid`, `subscription_start_date`, `renewal_date`, `cancellation_date`, `plan_type`, `contract_type`, `monthly_charges`, `cltv`, `churn_score`
3. **`db_support`**: `customerid`, `complaint_date`, `escalations`, `csat_score`, `cancellation_reason`, `comment`

---

## 🔄 Project Workflow & Roadmap

### 1. Data Ingestion & SQL Extraction
* Established Python database connection using `sqlite3`.
* Executed SQL queries (`JOIN`, `GROUP BY`, multi-table merging) to construct unified analytical datasets.

### 2. Data Cleaning & Preprocessing
* Handled missing/null values, standardized date formats, and transformed data types.
* Dropped redundant columns and performed quality check (QC) verifications.

### 3. Feature Engineering & Key Metrics
Engineered calculated fields and 20+ KPIs to model customer retention:
* **Average Tenure**: `AVG(DATEDIFF(cancellation_date, subscription_start_date))` = **1,451 days**
* **ARPU (Average Revenue Per User)**: `SUM(monthly_charges) / COUNT(active_customers)` = **$18.80**
* **Revenue Risk Scoring**: Quantified revenue leakage for customers with `churn_score > 70`.
* **Support Friction Correlation**: Analyzed correlation between support escalation rates and churn likelihood.

---

## 📊 Key Business Insights & Findings

| Metric / Analysis | Key Finding | Strategic Impact |
| :--- | :--- | :--- |
| **Contract Type** | Monthly churn is **55.6%** vs Annual churn at **8.3%**. | Shift acquisition campaigns toward annual plans to stabilize retention. |
| **Plan Type** | Majority of churned volume belongs to **Basic Tier** subscribers. | Lower immediate impact on overall revenue, but indicates entry-tier vulnerability. |
| **Geographic Spike** | **Karnataka** showed a significant churn anomaly in **September 2024**. | Warrants investigation into localized price changes, regional outages, or competitor activity. |
| **Support Escalations** | Higher escalation counts directly correlate with high churn scores. | Escalated support requests serve as an early warning indicator for proactive outreach. |

---

## 🚀 Actionable Recommendations

1. **Contract Migration Strategy**: Implement automated discount incentives for monthly subscribers converting to annual plans to reduce the 55.6% monthly churn rate.
2. **Targeted At-Risk Retention**: Filter accounts with high churn scores (`> 70`) and high CLTV to prioritize personalized retention offers (SMS/Email/Direct Calls) before cancellation.
3. **Regional Post-Mortem**: Investigate localized service complaints, pricing changes, or competitor promotional campaigns active in Karnataka during September 2024.

---

## ⚙️ How to Run Locally

### Prerequisites
* Python 3.8+
* Jupyter Notebook or JupyterLab

### Installation
```bash
# Clone the repository
git clone [https://github.com/your-username/churn-analysis-customer-intelligence.git](https://github.com/your-username/churn-analysis-customer-intelligence.git)
cd churn-analysis-customer-intelligence

# Install required packages
pip install pandas numpy matplotlib seaborn sqlite3
