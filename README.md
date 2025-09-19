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

# 4. Insights Deep Dive  

## 4.1 Customer Demographics  
- **Age Distribution (Customer Distribution by Age Group):**  
  Middle-aged (31–50) and Older (51–70) customers each account for ~37–38%, while Young (18–30) make up ~25–26%.  
  **Takeaway:** The customer base leans middle-aged/older, but value is not driven by age alone.
  
<img width="684" height="618" alt="output_7_0" src="https://github.com/user-attachments/assets/5e679b8d-1019-4381-a68b-08f16909fd79" />

- **Gender Distribution:**  
  Male (~350), Other (~330), and Female (~315) are fairly balanced.  
  **Takeaway:** Avoid gender-only targeting; gender segmentation should be combined with behavioral or category data.
  
<img width="692" height="539" alt="output_11_0" src="https://github.com/user-attachments/assets/58c2abda-38d8-4300-91a0-a92cd5df486e" />

---

## 4.2 Behavioral Insights  
- **Average Spending Score by Age Group:**  
  All age groups cluster around ~50–52, with middle-aged customers slightly higher.  
  **Takeaway:** Age alone is not a strong driver of spending score.

<img width="684" height="618" alt="output_8_1" src="https://github.com/user-attachments/assets/3a9aa82b-6fdf-43a3-8c2c-b78ee26a23aa" />


- **Average Purchase Frequency by Age Group:**  
  Young customers average ~27 purchases; middle-aged and older customers ~26. Differences are marginal.  
  **Takeaway:** Age does not meaningfully predict purchase frequency.

<img width="684" height="618" alt="output_9_1" src="https://github.com/user-attachments/assets/b76da08c-676a-4d41-8b03-6284d4b10448" />


- **Purchase Frequency Distribution by Age Group (Boxplot):**  
  Wide, overlapping distributions with medians around 26–28 purchases.  
  **Takeaway:** Within-group variance is high, so demographics are weak predictors. Use behavioral segmentation instead.

<img width="684" height="543" alt="output_10_1" src="https://github.com/user-attachments/assets/e30ca8e7-a5fc-4823-bc89-84eefd46c55c" />


- **Income vs Spending Score (Scatter):**  
  Shows no clear trend; spending scores are spread evenly across all income levels.  
  **Takeaway:** High income does not guarantee high engagement. This highlights a **high-income, low-score “untapped” customer group**.
  
<img width="692" height="543" alt="output_13_0" src="https://github.com/user-attachments/assets/c24f7fa9-4f54-467d-af1d-d5f4dfd42c67" />


- **Age vs Spending Score (Scatter):**  
  Flat cloud with no correlation.  
  **Takeaway:** Age is not a predictor of spending score; segment customers based on behavior.

<img width="692" height="543" alt="output_14_0" src="https://github.com/user-attachments/assets/e97ddbe7-d637-4df8-a70d-625f45b9960b" />


- **Distribution of Numerical Features (all histograms):**  
  Features such as age, income, spending_score, membership_years, purchase_frequency, and last_purchase_amount appear broadly uniform with wide ranges.  
  **Takeaway:** Expect weak simple correlations. Focus on clustering and engineered metrics like **CLV proxy = purchase_frequency × last_purchase_amount**.

<img width="975" height="737" alt="output_6_0" src="https://github.com/user-attachments/assets/ac2a63ff-13cf-42f4-a04f-a6453d6ae68e" />


---

## 4.3 Category Preferences  
- **Preferred Category Distribution:**  
  Electronics is the most popular, followed by Sports, Home & Garden, and Groceries. Clothing is least preferred.  
  **Takeaway:** Demand is diversified, but Electronics can anchor premium offers while Clothing may need bundling or discount strategies.

<img width="692" height="593" alt="output_12_0" src="https://github.com/user-attachments/assets/ca33f722-b758-4129-9571-e1e06470b30a" />


- **Average Spending Score by Category:**  
  All categories are similar (~49–52), with Clothing slightly higher and Home & Garden slightly lower.  
  **Takeaway:** Category preference alone does not strongly differentiate spending intensity. Combine category with purchase frequency and ticket size for better insights.

<img width="684" height="632" alt="output_16_0" src="https://github.com/user-attachments/assets/59511cf7-cfdb-4113-94a3-77e4087bc863" />


---

## 4.4 Correlation Snapshot  
- **Correlation Heatmap of Numerical Features:**  
  All correlations are close to zero (between -0.05 and +0.07).  
  **Takeaway:** No single variable drives another; clustering is appropriate.  
  **Engineered features to improve segmentation:**  
  - Customer Lifetime Value (CLV proxy): `purchase_frequency × last_purchase_amount`  
  - Tenure buckets derived from `membership_years`  
  - Monetary per visit: `last_purchase_amount` as basket proxy
 
<img width="881" height="654" alt="output_17_0" src="https://github.com/user-attachments/assets/f0fe8314-f4ce-4e2d-a386-ace557ef39a8" />


---

## 4.5 Segmentation Results (K-Means)  
- **Elbow Method for Optimal k:**  
  Clear drop at k=4–5, with diminishing returns afterward. k=5 chosen for interpretability.

<img width="700" height="466" alt="output_18_0" src="https://github.com/user-attachments/assets/5915db8d-3a45-4da5-9a5a-c882876d2996" />


- **Customer Segments (Income vs Spending Score, colored by cluster):**  
  Five actionable groups identified:  

  1. **Premium Loyalists** (high income, high spending score)  
     - High basket sizes and engagement.  
     - **Strategy:** Offer VIP perks, early access, and premium bundles.  

  2. **Untapped Potential** (high income, low spending score)  
     - Can afford more but low engagement.  
     - **Strategy:** Personalized campaigns, onboarding nudges, premium loyalty trials.  

  3. **Core Steady** (mid income, mid–high spending score)  
     - Reliable group, steady engagement.  
     - **Strategy:** Always-on campaigns, cross-sells, loyalty multipliers.  

  4. **Value Enthusiasts** (low income, high spending score)  
     - Frequent buyers, smaller baskets.  
     - **Strategy:** Promote bundles, discounts, and coupons to grow basket size.  

  5. **Budget Occasionals** (low income, low spending score)  
     - Infrequent and price-sensitive.  
     - **Strategy:** Target with seasonal promotions and reactivation campaigns.  

- **Takeaway:** Demographics alone are weak predictors. **Income + behavior create meaningful, actionable segments**.

<img width="671" height="543" alt="output_20_0" src="https://github.com/user-attachments/assets/f1929a07-d98f-4db4-b707-b75373b835bf" />
  
- **Next step:** Summarize clusters in a table with average age, income, frequency, last purchase, and top category to present to stakeholders.

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
