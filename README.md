# Customer Churn Analysis & Customer Intelligence

An end-to-end customer churn analysis project using SQL and Python to identify customer churn patterns, customer risk factors, and potential revenue impact.

**Author:** Nishant Kumar

**Tools:** Python, SQL, SQLite, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook

---

## About This Project

This project analyzes customer, subscription, and customer support data to understand why customers churn, which customer segments have higher churn, and how churn can affect revenue.

The analysis focuses on three key questions:

- **Who** is churning?
- **Why** are customers churning?
- **When** is churn occurring?

The project demonstrates an end-to-end data analytics workflow using SQL and Python, including data extraction, data cleaning, feature engineering, exploratory data analysis, visualization, and business insights.

This project was developed as part of my Data Analytics portfolio by following a guided data analytics tutorial and independently implementing and practicing the concepts in my own Jupyter Notebook.

---

## Business Problem

Customer churn is an important challenge for subscription-based businesses.

The objective of this project is to analyze customer behavior and identify patterns associated with churn.

The analysis looks at:

- Customer demographics
- Subscription plans
- Contract types
- Customer tenure
- Monthly charges
- Customer lifetime value (CLTV)
- Churn scores
- Customer complaints
- Support escalations
- Churn by geography
- Revenue impact of churn

The goal is to convert these findings into actionable recommendations that can support customer retention strategies.

---

## Dataset Structure

The project uses a SQLite database named `customer_churn` containing three relational tables.

### 1. `db_customer`

Contains customer demographic information.

| Column | Description |
|---|---|
| `customerid` | Unique customer identifier |
| `name` | Customer name |
| `country` | Customer country |
| `state` | Customer state |
| `gender` | Customer gender |
| `dob` | Date of birth |
| `interests` | Customer interests |
| `pincode` | Customer postal code |

### 2. `db_subscription`

Contains customer subscription and financial information.

| Column | Description |
|---|---|
| `customerid` | Unique customer identifier |
| `subscription_start_date` | Subscription start date |
| `subscription_type` | Subscription type |
| `renewal_date` | Renewal date |
| `plan_type` | Basic, Standard, or Premium |
| `contract_type` | Contract type |
| `cancellation_date` | Cancellation date |
| `cancellation_reason` | Reason for cancellation |
| `monthly_charges` | Monthly customer charges |
| `cltv` | Customer lifetime value |
| `churn_score` | Customer churn risk score |

### 3. `db_support`

Contains customer support information.

| Column | Description |
|---|---|
| `customerid` | Unique customer identifier |
| `complaint_date` | Complaint date |
| `escalations` | Number of escalations |
| `csat_score` | Customer satisfaction score |
| `comment` | Support comment |

---

## Tools & Technologies

### Programming & Analysis
- Python
- Pandas
- NumPy

### Database & SQL
- SQL
- SQLite
- `sqlite3`
- SQL queries executed from Python

### Data Visualization
- Matplotlib
- Seaborn

### Development Environment
- Jupyter Notebook

---

## Project Workflow

### 1. SQL Database Connection

Connected Python to the SQLite database using `sqlite3`.

SQL queries were used to extract relevant customer, subscription, and support data for analysis.

### 2. Data Cleaning

Performed data cleaning and quality checks using Pandas and NumPy.

Activities included:

- Checking data types
- Renaming columns
- Selecting required columns
- Checking missing values
- Handling null values
- Removing unnecessary columns
- Standardizing categorical values
- Converting date fields into appropriate formats

### 3. Feature Engineering

Created additional fields required for customer churn analysis.

The analysis included calculated attributes related to:

- Customer age
- Customer tenure
- Churn status
- Churn risk
- Subscription information
- Customer support activity

### 4. Data Analysis

Performed exploratory data analysis using:

- GroupBy
- Aggregations
- Filtering
- Pivot tables
- Churn rate calculations
- Segment-level analysis
- Correlation analysis

### 5. Data Visualization

Created visualizations using Matplotlib and Seaborn to understand:

- Monthly churn trends
- Churn by subscription plan
- Churn by state
- Relationships between customer attributes
- Correlation between churn-related variables
- Customer segment behavior

---

## Key Business Metrics

The project calculated several metrics to evaluate customer churn and its business impact.

### Churn Rate

```text
Churned Customers / Total Customers# Customer-Churn-Analysis
