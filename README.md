# Credit-Card-Customer-Segmentation-Profitability-Analysis

🧩 Project Overview

This project focuses on **analyzing credit card customer data** to uncover patterns in customer behavior, segment customers for targeted marketing, and predict churn risk using **machine learning**.  
The goal is to help a bank identify **high-value, at-risk, and loyal customer segments** — and design actionable strategies for retention and revenue growth.  

## 🗂️ Dataset
**Source:** Kaggle – Credit Card Customers Dataset  
**Records:** 10,127 customers  
**Fields:** Demographics, income, card type, credit limit, transaction amount & frequency, inactivity, churn flag, etc.
## Dataset Information
- **Rows:** 10,127  
- **Columns:** 21  
- **Key Features:**
  - `Customer_Age`, `Gender`, `Income_Category`, `Card_Category`
  - `Total_Trans_Amt`, `Total_Trans_Ct`, `Credit_Limit`, `Avg_Utilization_Ratio`
  - `Attrition_Flag` (Target Variable → “Existing” or “Attrited”)
---
## 🧩 Key Objectives
- Perform **RFM (Recency, Frequency, Monetary)** and **K-Means** clustering to group customers.
- Build a **Customer Lifetime Value (CLV)** model to measure long-term profitability.
- Develop **Profitability Tiers (Platinum → Standard)** and estimate ROI by customer group.
- Predict customer **churn risk using Random Forest** and identify key churn drivers.
- Generate actionable insights through **interactive visualizations (Plotly)**.

## 🗂️ Project Workflow

| Phase | Description | Tools Used |
|-------|--------------|-------------|
| **1. Data Setup** | Loaded and cleaned 10K+ customer records from Kaggle dataset | Pandas, NumPy |
| **2. EDA & Visualization** | Analyzed demographics, card usage, and behavior metrics | Matplotlib, Seaborn, Plotly |
| **3. Segmentation (RFM + Clustering)** | Grouped customers into 8 business segments (Loyal, At-Risk, etc.) | Scikit-learn (KMeans) |
| **4. Predictive Modeling** | Built Random Forest model to predict attrition risk (AUC = 0.93) | Scikit-learn |
| **5. CLV & Profitability Analysis** | Estimated revenue, cost, profit margin, and ROI per segment | Python, NumPy |
| **6. Reporting & Export** | Created final processed dataset for dashboards and reporting | CSV Export, Plotly |

---
## 🧮 Data Summary

| Metric | Value |
|--------|--------|
| Total Customers | 10,127 |
| Features | 46 |
| Attrition Rate | 16.07% |
| Avg. CLV | \$822 |
| Avg. ROI | 186% |
| Avg. Profit Margin | 34.6% |

---

## 📊 Key Insights

### 1️⃣ Portfolio Overview
- 16.1% attrition rate; majority are Blue cardholders.  
- Income group **< ₹40K** dominates base (~34%).  
- Gender distribution nearly balanced (53% F, 47% M).

### 2️⃣ Transaction Behavior
- Attrited customers show lower transaction counts, credit limits, and utilization ratios.  
- Transaction count (`Total_Trans_Ct`) has **0.81 correlation** with revenue.

### 3️⃣ Segmentation Summary (RFM-Based)
| Segment | % of Customers | Key Traits |
|----------|----------------|-------------|
| **Need Attention** | 19.2% | Moderate engagement, 24% churn |
| **Potential Loyalists** | 18.8% | Stable, profitable mid-tier |
| **Loyal Customers** | 11.8% | High value, low churn |
| **At Risk** | 11.7% | Declining engagement, watchlist |
| **Champions** | 4.1% | Most profitable, highest engagement |
| **Lost / Hibernating** | ~22% combined | Very low ROI |
| **Cannot Lose Them** | 1.3% | High churn (72%), urgent focus |

---
## 🤖 Predictive Modeling 

### 1. Customer Segmentation  
Identified 8 segments using RFM and K-Means clustering:  
- **Champions** 💎  
- **Loyal Customers**  
- **Potential Loyalists**  
- **At Risk**  
- **New Customers**  
- **Hibernating**  
- **Need Attention**  
- **Lost**

### 2. Churn Prediction  
Built a **Random Forest Classifier** to predict churn probability:  

| Metric | Score |
|---------|--------|
| **Accuracy** | 95% |
| **ROC-AUC** | 0.93 |
| **Precision (Churn)** | 0.88 |
| **Recall (Churn)** | 0.84 |

**Top Predictors of Churn:**
1. Lower Engagement Score  
2. Fewer Transactions  
3. High Months Inactive  
4. Low Credit Utilization

### 3. Customer Lifetime Value (CLV) Modeling  
Estimated customer value using:  
- 2.5% interchange fee on transactions  
- 18% annual interest on revolving balances  
- Segment-specific retention rates  

| Segment | Avg CLV (\$) |
|----------|--------------|
| Champions | 1,450 |
| Loyal Customers | 1,442 |
| Potential Loyalists | 928 |
| At Risk | 908 |
| Hibernating | 466 |

## 4. Profitability Analysis
| Segment | Avg. Transaction Amt | Total Revenue ($) | Churn % |
|----------|---------------------|------------------|---------|
| Loyal Customers | 10,183 | **12.2M** | 2.1 |
| Potential Loyalists | 4,444 | **8.4M** | 2.4 |
| At Risk | 4,754 | **5.6M** | 6.1 |
| Need Attention | 2,633 | **5.1M** | 24.0 |
| Champions | 10,558 | **4.4M** | 0.2 |
| Hibernating | 3,053 | 3.4M | 39.3 |
| New Customers | 2,471 | 2.6M | 9.6 |
| Lost | 1,589 | 1.8M | 32.0 |
| Cannot Lose Them | 6,454 | 0.86M | **72.4** |

🔹 **Top 35% of customers drive >75% of revenue.**  
🔹 “Need Attention” and “Hibernating” are **high-risk but recoverable** segments.  
🔹 “Cannot Lose Them” have high credit limits but minimal engagement → targeted recovery needed.

---
### 5. Profitability & ROI Analysis  
Classified customers into **Platinum, Gold, Silver, Bronze, and Standard** tiers based on CLV.  
Calculated **Net Profit, ROI, and Margin** for each segment.

| Tier | Avg CLV | Avg ROI | Margin |
|------|----------|----------|--------|
| Platinum | \$1,949 | 211% | 34.6% |
| Gold | \$1,315 | 186% | 31.7% |
| Silver | \$942 | 155% | 28.2% |
| Standard | \$200 | 76% | 17.4% |

### 6. K-Means Cluster Analysis
**Optimal K = 5 (Silhouette ≈ 0.20)**  
Clusters were named as follows:

| Cluster | Size | Avg Engagement | Churn % | Label |
|----------|------|----------------|----------|--------|
| 3 & 4 | 3,800 | 83–92 | 3–6 | **Premium High-Value** |
| 2 | 2,127 | 39 | 12 | **Growing Mid-Tier** |
| 0 | 2,767 | 38 | 35 | **Standard Active** |
| 1 | 1,434 | 36 | 15 | **Low Engagement** |

---
###  7. Customer Value Matrix (CLV × Churn Risk)
Developed a strategic 2×2 matrix to guide portfolio strategy:

| Category | Description | Action |
|-----------|--------------|---------|
| High Value – Retain | Active & profitable | Loyalty programs, premium offers |
| High Value – Win Back | Lost but valuable | Personalized retention campaigns |
| Low Value – Grow | Stable, low engagement | Cross-sell or upgrade |
| Low Value – Lost | Unprofitable, churned | Automated, low-cost communication |


## 8. Business Recommendations
| Segment | Suggested Action | Objective |
|----------|------------------|------------|
| **Champions / Loyal** | Offer tier upgrades, co-branded cards | Strengthen loyalty |
| **Potential Loyalists** | Cross-sell EMI/auto-debit | Increase spend frequency |
| **Need Attention** | Personalized reactivation offers | Prevent churn |
| **Hibernating / Lost** | Digital-only outreach | Cost efficiency |
| **Cannot Lose Them** | High-touch retention via RM calls | Recover profitability |

---

## 9. Business Impact
- Enables **targeted retention** focusing on 40% of customers who drive 85% profit.  
- Potential **profitability lift of 10–15%** through optimized customer engagement.  
- Framework can be directly used by BIU for portfolio monitoring.

---

## 10. Tools Used
Python, Pandas, NumPy, Matplotlib, Seaborn, Plotly, Scikit-learn

---










