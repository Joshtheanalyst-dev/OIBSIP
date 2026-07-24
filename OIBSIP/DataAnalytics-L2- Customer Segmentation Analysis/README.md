# Customer Segmentation Analysis using RFM & K-Means Clustering

## 📌 Project Overview

This project performs **customer segmentation** using **RFM (Recency, Frequency, Monetary) Analysis** and **K-Means Clustering** to group customers based on their purchasing behavior.

The objective is to identify valuable customer segments, understand customer behavior, and provide actionable business recommendations for improving customer retention, marketing campaigns, and revenue.

---

##  Dataset

The dataset contains transactional sales records from an e-commerce business, including:

- Customer ID
- Order Date
- Order Number
- Product Information
- Quantity Ordered
- Unit Price
- Unit Cost
- Discount Applied
- Shipping Information

After preprocessing, the data was aggregated into customer-level RFM metrics.

---

##  Project Objectives

- Clean and prepare transactional sales data
- Engineer customer revenue
- Compute RFM metrics
- Standardize features using StandardScaler
- Determine the optimal number of clusters using the Elbow Method
- Segment customers with K-Means Clustering
- Profile each customer segment
- Generate business insights and marketing recommendations

---

##  Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

##  Project Workflow

### 1. Data Loading & Inspection

- Imported the sales dataset
- Inspected data structure
- Checked for missing values
- Checked for duplicate records

---

### 2. Data Cleaning

Performed the following preprocessing steps:

- Converted `CustomerID` to string
- Converted date columns to datetime
- Verified data quality
- Prepared data for analysis

---

### 3. Feature Engineering

Created a new **Revenue** column using:

```text
Revenue = (Unit Price − (Unit Price × Discount Applied) − Unit Cost)
          × Order Quantity
```

This represents the profit generated from each transaction.

---

### 4. RFM Analysis

Calculated three customer metrics:

| Metric | Description |
|---------|-------------|
| Recency | Days since customer's last purchase |
| Frequency | Number of orders placed |
| Monetary | Total revenue generated |

---

### 5. Feature Scaling

Used **StandardScaler** to normalize the RFM features before clustering.

Scaling ensures that no single feature dominates the clustering process due to differences in scale.

---

### 6. Finding the Optimal Number of Clusters

Applied the **Elbow Method** to determine the optimal value of **K**.

The analysis indicated:

**Optimal K = 4**

---

### 7. Customer Segmentation

Built a **K-Means Clustering** model with:

- K = 4 clusters

Each customer was assigned to one of four behavioral groups.

---

### 8. Cluster Visualization

Visualized customer clusters using scatter plots:

- Recency vs Frequency
- Frequency vs Monetary Value

These plots help illustrate how customers are distributed across the identified segments.

---

### 9. Customer Profiling

Calculated the average RFM values for each cluster to understand customer behavior and assign meaningful business labels.

The resulting customer segments are:

-  Champions
-  Loyal Customers
-  Regular Customers
-  Lost Customers

---

##  Key Insights

- Champions represent the most valuable customers with recent purchases, high purchase frequency, and high monetary value.
- Loyal Customers purchase frequently and contribute consistently to revenue.
- Regular Customers show moderate engagement and have potential for growth.
- Lost Customers make up the largest customer group and require re-engagement strategies.

---

##  Business Recommendations

- Reward Champions with exclusive offers and loyalty programs.
- Retain Loyal Customers through personalized promotions.
- Encourage Regular Customers with targeted upselling and cross-selling campaigns.
- Re-engage Lost Customers using discounts, email marketing, or win-back campaigns.

---

##  Repository Structure

```
customer-segmentation-analysis/
│
├── customer-segmentation-analysis.ipynb
├── README.md
└── images/               # (Optional: plots and visualizations)
```

---

##  Future Improvements

- Evaluate cluster quality using Silhouette Score
- Experiment with Hierarchical and DBSCAN clustering
- Build an interactive Power BI dashboard
- Deploy the segmentation model as a web application

---

##  Author

**Akubueze Joshua**

- LinkedIn: https://www.linkedin.com/in/akubueze-joshua-0586b33b3
- Kaggle: https://www.kaggle.com/code/joshthegreat

---

##  If you found this project helpful...

Consider giving the repository a **star ⭐** to support the project.
