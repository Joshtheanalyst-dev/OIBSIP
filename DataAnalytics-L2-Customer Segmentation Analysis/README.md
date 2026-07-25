# Customer Segmentation Analysis — RFM + KMeans Clustering

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green?logo=pandas)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-KMeans-orange?logo=scikit-learn)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-teal)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Charts-red)
![Kaggle](https://img.shields.io/badge/Kaggle-Notebook-20BEFF?logo=kaggle)

## 📌 Project Overview

This project applies **RFM Analysis** combined with **KMeans Clustering** to segment an e-commerce company's customer base into distinct behavioural groups — enabling targeted marketing strategies for each segment.

Rather than treating all customers the same, this analysis identifies exactly who the VIPs are, who is at risk of churning, and who represents the greatest growth opportunity.

**Dataset:** Customer Sales Dataset (E-commerce transactions)
**Notebook:** [View Full Analysis on Kaggle](https://www.kaggle.com/code/joshthegreat/customer-segmentation-analysis)

---

## Objectives

- Load and preprocess customer sales transaction data
- Engineer RFM features (Recency, Frequency, Monetary Value) per customer
- Normalise features using StandardScaler before clustering
- Determine optimal number of clusters using the Elbow Method
- Apply KMeans clustering (K=4) to segment customers
- Profile and label each cluster with meaningful business segment names
- Visualise clusters using scatter plots
- Deliver actionable marketing recommendations per segment

---

## Dataset Description

| Column | Description |
|---|---|
| CustomerID | Unique customer identifier |
| OrderNumber | Unique order identifier |
| OrderDate | Date of transaction |
| ShipDate | Date order was shipped |
| DeliveryDate | Date order was delivered |
| Unit Price | Price per unit before discount |
| Unit Cost | Cost per unit |
| Discount Applied | Discount rate applied to the order |
| Order Quantity | Number of units ordered |

**Shape:** 50 unique customers across multiple transactions
**Missing Values:** None
**Duplicates:** None

---

##  Tech Stack

- **Python 3.x**
- **Pandas** — data manipulation and feature engineering
- **NumPy** — numerical operations
- **Scikit-learn** — StandardScaler, KMeans clustering
- **Matplotlib** — base visualizations
- **Seaborn** — scatter plots and cluster visualizations
- **Jupyter Notebook** — development environment (Kaggle)

---

##  Analysis Workflow

### 1. Data Loading & Inspection
- Loaded dataset and inspected structure, dtypes, nulls and duplicates
- No missing values or duplicate rows found

### 2. Data Cleaning & Type Corrections
- CustomerID converted to string (identifier, not numeric)
- OrderDate, ShipDate, DeliveryDate converted to datetime
- Column names standardised by removing underscores

### 3. Feature Engineering — Revenue
Revenue was calculated using actual **profit per order** formula:
```
Revenue = (Unit Price − (Unit Price × Discount) − Unit Cost) × Order Quantity
```

### 4. RFM Feature Computation
Each customer aggregated into 3 behavioural dimensions:

| Feature | Definition |
|---|---|
| **Recency** | Days since last purchase (reference: 2021-01-01) |
| **Frequency** | Total number of orders placed |
| **Monetary Value** | Total profit generated |

### 5. Data Normalisation
StandardScaler applied to ensure all RFM features contribute equally to clustering — preventing larger-scale features from dominating distance calculations.

### 6. Elbow Method
Inertia plotted for K=1 to K=10. Elbow identified at **K=4** — selected as optimal number of clusters.

### 7. KMeans Clustering
KMeans applied with K=4 and fixed random_state for reproducibility. Each customer assigned to one of 4 clusters.

### 8. Cluster Visualisation
Two scatter plots produced:
- Recency vs Frequency
- Frequency vs Monetary Value

### 9. Cluster Profiling & Segment Naming
Clusters mapped to business segment names based on actual RFM profiles.

---

##  Segment Results

| Segment | Customers | Avg Recency | Avg Frequency | Avg Monetary Value |
|---|---|---|---|---|
|  **VIP** | 1 | 3.0 days | 210.0 orders | $616,719 |
|  **Champions** | 22 | 6.0 days | 169.4 orders | $467,719 |
|  **Regular Customers** | 23 | 5.9 days | 148.8 orders | $377,702 |
|  **At Risk** | 4 | 21.0 days | 157.8 orders | $432,911 |

**Total customers analysed: 50**

---

##  Key Business Recommendations

###  VIP (1 Customer)
A single customer generating $616,719 in monetary value — the highest of any segment. Assign a dedicated account manager, offer exclusive access, and build a personal relationship. This customer cannot be treated like a regular account.

###  Champions (22 Customers — 44%)
The revenue engine of the business. Enroll in VIP loyalty programmes, request referrals, and send personalised appreciation campaigns. Do not over-discount — they already buy at full price.

### Regular Customers (23 Customers — 46%)
The largest segment and closest to Champion status in recency. Focus on increasing frequency and basket size through bundle offers and cross-sell campaigns. The highest growth opportunity in the business.

### ⚠️ At Risk (4 Customers — 8%)
Haven't purchased in 21 days despite historically strong RFM profiles. Launch an immediate personalised win-back campaign with a time-sensitive offer. If no response after 2 attempts, reassess investment in this segment.

---

##  Repository Structure

```
customer-segmentation-analysis/
│
├── customer_segmentation_analysis.ipynb    # Main Jupyter Notebook
├── README.md                               # Project documentation
└── data/
    └── sales_data.csv                      # Raw dataset
```

---

##  How to Run

1. Clone this repository:
```bash
git clone https://github.com/joshthegreat/customer-segmentation-analysis.git
```

2. Install required libraries:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

3. Open the notebook:
```bash
jupyter notebook customer_segmentation_analysis.ipynb
```

Or view directly on Kaggle:
👉 (https://www.kaggle.com/code/joshthegreat/customer-segmentation-analysis)

---

## Key Takeaways

- **90% of customers are recently active** — Champions and Regular Customers combined represent a remarkably healthy customer base
- **The VIP customer is a business-critical asset** — a single customer whose RFM scores dwarf every other segment
- **Regular Customers are the biggest growth opportunity** — one targeted campaign could convert a significant portion to Champions
- **At Risk customers need immediate action** — their historical value justifies high-touch personalised outreach right now

---

##  Author

**Akubueze Joshua**
Data Analyst | Marketing Analytics Specialist

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://www.linkedin.com/in/akubueze-joshua-0586b33b3)
[![Portfolio](https://img.shields.io/badge/Portfolio-Visit-green)](https://akubuezejoshuaportfolio.lovable.app)
[![Kaggle](https://img.shields.io/badge/Kaggle-Profile-20BEFF?logo=kaggle)](https://www.kaggle.com/code/joshthegreat)

---

*This project was completed as Task 2 of a Data Analyst Internship program.*
