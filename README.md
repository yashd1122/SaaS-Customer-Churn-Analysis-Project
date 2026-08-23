# SaaS Customer Churn Analysis

**End-to-End Project**  
*Transforming raw SaaS data into actionable retention insights*

---

## Business Problem

In the SaaS industry, **acquiring new customers is 5–25× more expensive** than retaining existing ones.  
**Ravenstack** (a simulated B2B SaaS company) is facing a **9.9% churn rate**, putting **₹2.04 Crore in Annual Recurring Revenue (ARR)** at immediate risk.

This project aims to answer:
- Which customer segments are churning the most?
- What are the main reasons customers leave?
- How much revenue is at risk and why?
- What actionable steps can reduce churn?

---

## 📁 Dataset Overview

Five interconnected datasets were used:

| File                            | Rows   | Description                              |
|--------------------------------|--------|------------------------------------------|
| `ravenstack_accounts.csv`       | 500    | Account metadata                         |
| `ravenstack_subscriptions.csv`  | 5,000  | Subscription details (plan, MRR, dates)  |
| `ravenstack_feature_usage.csv`  | 25,000 | Feature usage logs                       |
| `ravenstack_support_tickets.csv`| 2,000  | Support ticket history                   |
| `ravenstack_churn_events.csv`   | 600    | Churn events + customer feedback         |

**Final Master Table:** 7,429 subscriptions after joining and feature engineering.

**Key Features Created:**
- `churn_flag`
- `tenure_months`
- `ticket_count`
- `avg_feature_usage`

---

## 🔥 Key Business Insights

### 1. Overall Snapshot
| Metric              | Value              | Insight                              |
|---------------------|--------------------|--------------------------------------|
| Total Subscriptions | 7,429              | Healthy customer base                |
| Churn Rate          | **9.9%**           | Above healthy SaaS benchmark (5–7%)  |
| Active MRR          | **₹1.48 Cr**       | Strong recurring revenue             |
| **ARR at Risk**     | **₹2.04 Cr**       | High priority — needs immediate action |

### 2. Churn by Plan Tier
- **Pro Plan** has the **highest churn rate (10.3%)**
- Enterprise has the highest absolute revenue at risk
- Basic plan is relatively more stable

### 3. Critical Finding: Early Churn Problem
- Customers who churn stay only **2.83 months** on average vs **21.37 months** for active customers.
- Very high churn observed in the **first 6 months**.

### 4. Behavioral Difference
- Churned customers use **dramatically fewer features** (7,333 vs 66,481).
- Clear signal that low engagement is a strong leading indicator of churn.

---

## 📊 Tableau Dashboard

I built an interactive Tableau dashboard to visualize churn patterns and communicate insights effectively.

### Dashboard Screenshots!


**Main Dashboard Overview**
<img width="1593" height="789" alt="image" src="https://github.com/user-attachments/assets/5b9c49b5-6299-4b3a-96e1-f08fd0ce055f" />

**Churn Rate by Tenure Group**
<img width="1452" height="767" alt="image" src="https://github.com/user-attachments/assets/1bed832c-0cde-4da8-9c22-872ded27dc10" />


**Average Tenure - Active vs Churned**
<img width="1440" height="778" alt="image" src="https://github.com/user-attachments/assets/1121d932-7924-4252-b8b2-8d6df68ad0d9" />



**Average Feature Usage - Active vs Churned**
<img width="1446" height="774" alt="image" src="https://github.com/user-attachments/assets/7caac5ed-95a6-486e-a955-62c9aaabde87" />



### Key Takeaways from Dashboard
- **100% churn rate** observed in the first 6 months for many customer segments.
- Churned customers show significantly lower engagement (feature usage).
- Pro plan needs urgent attention due to highest churn rate.

---

## 🛠️ Tools & Technologies Used

- **Python 3.13** (pandas, sqlite3)
- **Jupyter Notebook**
- **Tableau** (for interactive dashboard)
- **SQL** for data preparation and analysis

---

## 💡 Business Recommendations

1. **Focus on Onboarding** — High churn in the first 6 months indicates onboarding or expectation mismatch issues.
2. **Investigate Pro Plan** — Highest churn rate. Review pricing, value delivered, and onboarding for this tier.
3. **Drive Feature Adoption** — Low feature usage is a strong predictor of churn. Create in-app guidance and adoption campaigns.
4. **Early Intervention** — Build alerts for customers showing low engagement in the first 3 months.

---

## 📈 Project Impact

This project demonstrates a complete churn analysis workflow — from raw data to actionable business recommendations. The insights can directly help reduce revenue leakage and improve customer retention.
