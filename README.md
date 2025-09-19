# customer-segmentation-retail
Customer segmentation analysis for a multi-category retail store. Explores demographics, spending behavior, and shopping preferences using Python and K-Means clustering to identify actionable marketing strategies and improve customer retention.


## 1. Background & Overview  
This project analyzes customer data from a **multi-category retail store**.  

**Business Goal:**  
Identify **key customer segments** to help marketing teams:  
- Target customers with personalized campaigns  
- Improve retention  
- Increase customer lifetime value  

---

## 2. Data Structure Overview  
Dataset: **1,000 customers**  

| Column | Description |
|--------|-------------|
| age | Customer’s age |
| gender | Gender identity (Male, Female, Other) |
| income | Annual income (USD) |
| spending_score | Relative measure of customer’s shopping activity (1–100) |
| membership_years | Number of years in loyalty program |
| purchase_frequency | Number of purchases per year |
| preferred_category | Primary shopping category |
| last_purchase_amount | Value of last purchase (USD) |

---

## 3. Executive Summary  
➡️ **Replace this with 3–4 sentences about your main findings.**  
- Example: “Middle-aged customers form the largest share, but young customers (18–30) have the highest spending score and purchase frequency. High-income customers make larger individual purchases but aren’t always engaged overall. Clustering revealed 5 distinct customer groups with unique behaviors.”  

---

## 4. Insights Deep Dive  

### 4.1 Customer Demographics  
- **Finding:** [Insert % breakdown of age groups]  
- **So what?** [Insert why it matters]  

### 4.2 Behavioral Insights  
- Age vs Spending Score → [insert what you found]  
- Age vs Purchase Frequency → [insert what you found]  
- Income vs Last Purchase Amount → [insert correlation/insight]  

### 4.3 Category Preferences  
- [Insert finding: e.g., Electronics have highest avg purchase, Groceries dominate volume]  

### 4.4 Segmentation Results (K-Means)  
- Cluster 0 – Premium Loyalists: [your summary stats]  
- Cluster 1 – Price-Sensitive: [your summary stats]  
- Cluster 2 – Untapped Potential: [your summary stats]  
- Cluster 3 – Young Frequent Shoppers: [your summary stats]  
- Cluster 4 – Occasional Shoppers: [your summary stats]  

---

## 5. Recommendations  
➡️ **List 3–5 business actions**. Example:  
- Strengthen loyalty perks for Cluster 0.  
- Target Cluster 2 with engagement campaigns.  
- Upsell to young frequent shoppers.  

---

## 6. Caveats & Assumptions  
- Synthetic dataset, not real customers  
- No time series analysis possible  
- Spending Score = index, not actual $  

---

## 7. Technical Details (One Click Away)  
- [Jupyter Notebook](./notebooks/customer_segmentation.ipynb)  
- [Data Source – Kaggle](https://www.kaggle.com/datasets/fahmidachowdhury/customer-segmentation-data-for-marketing-analysis)  

---

## 8. Tools & Skills Highlighted  
- Python (Pandas, Matplotlib, Seaborn, Scikit-Learn)  
- Customer segmentation & clustering  
- Business storytelling with data  
