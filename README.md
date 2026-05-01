# Customer-Segmentation-RFM-K-Means-
Segmented 90,000+ retail transactions using RFM scoring and K-Means clustering (K=4) to classify customers into 8 behavioral groups with targeted retention strategies.

# 👥 Customer Segmentation — RFM Analysis + K-Means Clustering

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-F7931E?logo=scikit-learn)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange)
![xlsxwriter](https://img.shields.io/badge/xlsxwriter-Excel%20Report-217346)
![Level](https://img.shields.io/badge/Level-Intermediate-yellow)

---

## 📌 Project Overview

This project segments customers of a UK-based online gift retailer using the **RFM (Recency, Frequency, Monetary)** framework combined with **K-Means clustering**. The goal is to identify behaviorally distinct customer groups from raw transaction data and translate them into targeted business actions.

**Business Question:** Which customers are most valuable, which are at risk of churning, and what actions should be taken for each group?

---

## 📂 Project Structure

```
Customer segmentation(intermediate)/
│
├── online_retail_rfm (1).csv              # Dataset — 90,097 rows, 8 columns
├── Customer_Segmentation_RFM.ipynb        # 9-module, 43-cell analysis notebook
└── README.md
```

---

## 📊 Dataset

| Attribute | Details |
|---|---|
| **Source** | [Online Retail II UCI — Kaggle](https://www.kaggle.com/datasets/mashlyn/online-retail-ii-uci) |
| **Records** | 90,097 transaction rows |
| **Unique Customers** | 3,977 |
| **Unique Invoices** | 20,000 |
| **Total Revenue** | £3,955,270 |
| **Countries** | 8 (UK dominant) |
| **Period** | December 2009 – December 9, 2011 |
| **File** | `online_retail_rfm (1).csv` |

**Columns:** `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`

---

## 🎯 Project Objectives

1. Compute RFM scores for all 3,977 customers from raw transaction data
2. Create rule-based segments using RFM quintile banding
3. Apply K-Means clustering and select optimal K via Elbow + Silhouette
4. Evaluate clustering quality with Silhouette Score
5. Provide segment-level business recommendations
6. Generate a multi-sheet Excel dashboard with `xlsxwriter`

---

## 🔧 Tools & Technologies

| Tool | Purpose |
|---|---|
| Python 3 | Core language |
| pandas | Transaction aggregation, RFM calculation |
| NumPy | Normalization |
| Matplotlib | Segment bar charts, scatter plots, elbow curve |
| Seaborn | Heatmaps, cluster visualizations |
| scikit-learn | KMeans, StandardScaler, silhouette_score |
| xlsxwriter | Excel report generation |
| Jupyter Notebook | 9-module, 43-cell analysis |

---

## 📈 Analysis Workflow (9 Modules)

| Module | Description |
|---|---|
| 1 | Data loading — 90,097 rows, inspect structure |
| 2 | Data cleaning — remove cancellations (InvoiceNo starting with 'C'), nulls, negative quantities |
| 3 | RFM calculation — Recency (days since last purchase), Frequency (invoice count), Monetary (total spend) |
| 4 | RFM scoring — quintile-based 1–5 scores per dimension |
| 5 | Rule-based segmentation — 8 named segments |
| 6 | Business insights per segment |
| 7 | K-Means clustering — Elbow method + Silhouette analysis |
| 8 | Excel report with `xlsxwriter` |
| 9 | Final summary and business recommendations |

---

## 📊 Visualizations

| # | Chart | Insight |
|---|---|---|
| 1 | 3-panel histogram | RFM metric distributions — Recency, Frequency, Monetary |
| 2 | Horizontal bar | Customer count by RFM segment |
| 3 | Donut chart | Revenue share by customer segment |
| 4 | Scatter (PCA space) | K-Means clusters visualized in 2D (PC1 vs PC2) |
| 5 | Elbow + Silhouette (dual panel) | Optimal K selection — WCSS and silhouette scores for K=2-10 |
| 6 | Heatmap | Average Monetary value by Recency Score × Frequency Score |
| 7 | Radar/Spider chart | Avg RFM scores per cluster (overlapping polygons) |
| 8 | Bar chart | Top 10 customers by total revenue |
| 9 | Area + line | Monthly revenue trend (Jan 2009 – Dec 2011) |
| 10 | Grouped bar (dual axis) | Cluster revenue vs customer count comparison |

---

## 🏷️ Customer Segments

| Segment | Description | Recommended Action |
|---|---|---|
| **Champions** | High R, F, M — bought recently, often, most | Reward — VIP loyalty program |
| **Loyal Customers** | High frequency — buy regularly | Upsell, cross-sell premium products |
| **Potential Loyalists** | Recent + moderate frequency | Nurture with personalized campaigns |
| **At Risk** | Were high-value, haven't bought recently | Win-back campaign with special offer |
| **Hibernating** | Low R, F, M — inactive for months | Re-engagement emails |
| **New Customers** | Recent first-time buyers | Onboarding sequence (60-day) |
| **Lost** | Very long since last purchase | Final low-cost reactivation or suppress |
| **Big Spenders** | High M but low frequency | Encourage repeat purchase |

---

## 📋 Excel Report

Output: `Customer_Segmentation_RFM_Report.xlsx`

**KPI table in the report includes:**
- Total Customers Analyzed
- Total Revenue
- Average Revenue per Customer
- Average Purchase Frequency
- Average Recency (days)
- Top 10% Customer Revenue Share
- Number of Segments (Rule-Based)
- Number of Clusters (K-Means)
- K-Means Silhouette Score
- Champion Customers count

---

## 🔍 Key Findings (Verified from Dataset)

| Metric | Value |
|---|---|
| Total transactions | 90,097 rows |
| Unique customers | 3,977 |
| Total revenue | £3,955,270 |
| Date range | Dec 2009 – Dec 2011 |
| Top country | United Kingdom |

- Classic **Pareto distribution** confirmed — top 10% of customers account for the majority of total revenue
- **Recency** is the strongest predictor of future purchase — customers silent for 90+ days rarely return without intervention (stated in notebook final summary)
- K-Means Silhouette Score confirms statistically meaningful cluster separation
- **Champions** and **Loyal Customers** are the highest-priority retention targets

---

## 💡 Business Recommendations (from Notebook)

| Segment | Action |
|---|---|
| Champions | Enroll in VIP loyalty program, offer early product access |
| At Risk | Win-back email with 15% discount within 30 days |
| New Customers | Automated 60-day onboarding email sequence |
| Lost Customers | One final re-engagement campaign; suppress from paid channels |
| Potential Loyalists | Cross-sell campaigns based on purchase history |

---

## 🚀 How to Run

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xlsxwriter

jupyter notebook Customer_Segmentation_RFM.ipynb
# Output: Customer_Segmentation_RFM_Report.xlsx
```

---

## 👤 Author

**[ABITHA ]** | [LinkedIn](https://www.linkedin.com/in/abitha-s-105663399?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app) | [GitHub](https://github.com/AbithaSenthil)
