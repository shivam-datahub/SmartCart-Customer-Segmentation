# SmartCart-Customer-Segmentation
An end-to-end unsupervised machine learning project segmenting 2,200+ e-commerce customers using K-Means clustering and PCA to drive targeted marketing and customer retention.
# 🛒 SmartCart Customer Segmentation System

An end-to-end unsupervised machine learning pipeline designed to segment e-commerce customers based on purchasing behavior, engagement metrics, and demographic profiles.

---

## 📌 Problem Statement
SmartCart is a global e-commerce platform serving customers across multiple regions[cite: 1]. With 2,240 customer records and 22 attributes[cite: 1], the platform previously relied on generic marketing strategies. This one-size-fits-all approach led to:
- Inefficient marketing spend[cite: 1].
- Missed retention opportunities for high-value shoppers[cite: 1].
- Delayed identification of churn-prone users[cite: 1].

This project builds an intelligent customer segmentation system using unsupervised machine learning algorithms (K-Means / Hierarchical Clustering) to enable targeted marketing strategies and data-driven customer retention[cite: 1].

---

## 📊 Dataset Overview
The dataset contains 2,240 customer profiles across four main feature categories[cite: 1]:

| Category | Key Attributes |
| :--- | :--- |
| **Demographics** | `ID`, `Year_Birth`, `Education`, `Marital_Status`, `Income`, `Kidhome`, `Teenhome`, `Dt_Customer`[cite: 2] |
| **Spending (Amount Spent)** | `MntWines`, `MntFruits`, `MntMeatProducts`, `MntFishProducts`, `MntSweetProducts`, `MntGoldProds`[cite: 2] |
| **Purchasing Frequency** | `NumDealsPurchases`, `NumWebPurchases`, `NumCatalogPurchases`, `NumStorePurchases`, `NumWebVisitsMonth`[cite: 2] |
| **Feedback & Engagement** | `Recency`, `Complain`, `Response`[cite: 3, 4] |

---

## 🛠️ Data Preprocessing & Feature Engineering
To prepare the dataset for clustering, the following pipeline was executed[cite: 4]:

1. **Missing Value Imputation**: Imputed missing `Income` values using the median income[cite: 4].
2. **Age Derivation**: Calculated customer `Age` relative to the current reference period (`2026 - Year_Birth`)[cite: 4].
3. **Tenure Calculation**: Converted customer enrollment dates (`Dt_Customer`) into `Customer_tenure_days`[cite: 4].
4. **Feature Aggregation**:
   - `Total_Spending`: Summed spend across all 6 product categories[cite: 4].
   - `Total_Children`: Combined `Kidhome` and `Teenhome`[cite: 4].
5. **Categorical Simplification**:
   - Grouped `Education` into `Undergraduate`, `Graduate`, and `Postgraduate`[cite: 4].
   - Simplifed `Marital_Status` into `Living_With` (`Partner` vs. `Alone`)[cite: 4].
6. **Dimensionality Reduction & Cleanup**: Dropped redundant individual spending metrics and date fields after aggregation[cite: 4].

---

## ⚙️ Tech Stack & Libraries
- **Language**: Python 3.x
- **Data Manipulation**: `pandas`, `numpy`[cite: 4]
- **Visualization**: `matplotlib`, `seaborn`[cite: 4]
- **Machine Learning**: `scikit-learn` (StandardScaler, K-Means, PCA)

---

## 🚀 Key Results & Business Impact
- **Personalized Campaigns**: Segments enable tailored discount strategies for high-deal-seeking shoppers vs. premium buyers.
- **Churn Reduction**: Identifies low-frequency, high-recency buyers for targeted win-back email sequences.
- **Resource Optimization**: Directs high-cost catalog marketing strictly to top-spending clusters.

---

## 🔧 Installation & Usage

```bash
# Clone repository
git clone [https://github.com/](https://github.com/)<your-username>/SmartCart-Customer-Segmentation.git
cd SmartCart-Customer-Segmentation

# Install dependencies
pip install -r requirements.txt

# Run the notebook
jupyter notebook notebooks/smartcart_clustering.ipynb
