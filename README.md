# 🛒 E-Commerce Customer Segmentation Analysis

## 📌 Overview
This project applies **RFM-based (Recency, Frequency, Monetary) analysis** and **K-Means clustering** to segment over **10,000 online retail transactions**.  
The goal is to uncover distinct customer groups based on purchasing behavior and spending patterns to drive **targeted marketing, retention strategies, and revenue growth**.

---

## ⚙️ Key Features
- Data cleaning and preprocessing  
- Exploratory data analysis (EDA) using histograms, heatmaps, and correlation analysis  
- RFM (Recency, Frequency, Monetary) feature engineering  
- Log transformation and standardization  
- K-Means clustering with Elbow and Silhouette evaluation  
- Customer persona profiling (mean and median RFM values)  
- Interactive visualization dashboard with scatter plots, boxplots, and heatmaps

---

## 💻 Tech Stack
- **Language:** Python  
- **Libraries:**  
  - `pandas`, `numpy` for data handling  
  - `matplotlib`, `seaborn` for visualizations  
  - `scikit-learn` (`StandardScaler`, `KMeans`, `silhouette_score`) for clustering and evaluation

---

## 📂 Dataset
- **File:** `online_retail_10k.csv`  
- Contains 10,000 transaction records with the following key fields:  
  - `customer_id`  
  - `transaction_id`  
  - `transaction_date`  
  - `quantity`  
  - `unit_price`  
  - `transaction_amount`

---

## 🚀 Project Workflow

### 1. Data Cleaning
- Converted and validated dates and numeric fields  
- Fixed mismatched transaction amounts (`quantity * unit_price`)  
- Handled negative amounts (returns/cancellations)  
- Winsorized outliers and imputed missing values

### 2. Exploratory Data Analysis (EDA)
- Visualized distributions of `quantity`, `unit_price`, and `transaction_amount`  
- Correlation heatmap revealed a strong positive link between quantity and transaction amount

### 3. RFM Feature Engineering
- **Recency:** Days since last purchase  
- **Frequency:** Number of transactions  
- **Monetary:** Total spending  
- Applied log transformation and standardization for clustering

### 4. Clustering
- Applied **K-Means** with `k = 3–6`  
- Evaluated clusters using Elbow method (inertia) and Silhouette score  
- **Best k = 3**, with a **Silhouette Score of 0.48**

### 5. Cluster Profiles
| Cluster | Recency (mean) | Frequency (mean) | Monetary (mean) | Description                    |
|---------|----------------|------------------|------------------|--------------------------------|
| 1       | 42.8 days       | 8.2               | 14,891.9           | High-value loyal customers |
| 0       | 39.2 days       | 4.3               | 7,160.7              | Mid-tier potential customers |
| 2       | 817.0 days     | 4.2               | 7,375.7              | Churned / At-risk customers |

- **Cluster 1:** Loyal, frequent, high spenders  
- **Cluster 0:** Recent buyers with moderate engagement  
- **Cluster 2:** Inactive, at-risk customers needing re-engagement

---

## 📈 Sample Results
Here are some of the key visual outputs generated:

![Elbow Method for Optimal k (Inertia vs k)](visuals/elbow_method.png)
![Recency vs Frequency by Cluster](visuals/recency_frequency_clusters.png)
![Normalized RFM Profile by Cluster](visuals/rfm_profile_heatmap.png)

---

## 💡 Business Insights
- **High-value customers (Cluster 1):** Offer loyalty rewards, VIP access, and referral programs  
- **At-risk customers (Cluster 2):** Launch re-engagement campaigns with discounts  
- **Potential customers (Cluster 0):** Promote cross-sell/upsell to convert them into loyal buyers
