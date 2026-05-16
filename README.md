# SaaS Customer Churn Analysis

**End-to-End Project**  
*Transforming raw SaaS data into actionable retention insights*

---

## Business Problem

In the highly competitive SaaS industry, **acquiring new customers is 5–25× more expensive** than retaining existing ones. 

**Ravenstack** (a simulated B2B SaaS company) is experiencing a **9.9% churn rate**, putting **₹2.04 Cr in Annual Recurring Revenue (ARR) at risk**.

This project answers critical questions:
- Which customer segments are churning the most?
- What are the top reasons customers leave?
- How much revenue is leaking, and why?
- What quick wins can reduce churn?

---

## 📁 Dataset Overview

Five rich, interconnected datasets (simulated for educational purposes):

| File                        | Rows   | Description                              |
|-----------------------------|--------|------------------------------------------|
| `ravenstack_accounts.csv`   | 500    | Account metadata (industry, etc.)        |
| `ravenstack_subscriptions.csv` | 5,000 | Core subscription data (plan, MRR, dates)|
| `ravenstack_feature_usage.csv` | 25,000 | Feature usage logs per subscription     |
| `ravenstack_support_tickets.csv` | 2,000 | Support ticket history                   |
| `ravenstack_churn_events.csv` | 600   | Churn events + verbatim feedback         |

**Total Master Table:** 7,429 subscriptions after joining & feature engineering.

---

- **Language:** Python 3.13
- **Libraries:** pandas, sqlite3, collections
- **Tools:** Jupyter Notebook, SQLite, Tableau/Power BI ready export
- **Approach:** SQL-first analysis for scalability + transparency

**Key Features Engineered:**
- `churn_flag` (1 = churned)
- `tenure_months` (precise using JULIANDAY)
- `ticket_count` (per account)
- `avg_usage` (mean feature usage)

---

## 🔥 Key Business Insights

### 1. Overall Health Snapshot
| Metric                  | Value          | Business Interpretation                  |
|-------------------------|----------------|------------------------------------------|
| Total Subscriptions     | 7,429          | Healthy customer base                    |
| Churn Rate              | **9.9%**       | Slightly above healthy SaaS benchmark (5–7%) |
| Active MRR              | **₹1.48 Cr**    | Strong recurring revenue                 |
| **ARR at Risk**         | **₹2.04 Cr**    | **High priority** — immediate action needed |

### 2. Churn by Plan Tier (Highest Risk First)
| Plan Tier   | Churn Rate | Subscriptions | Revenue Risk Insight                     |
|-------------|------------|---------------|------------------------------------------|
| **Pro**     | **10.3%**  | 2,467         | Highest churn — pricing/value mismatch?  |
| Enterprise  | 9.9%       | 2,551         | Highest absolute revenue at risk         |
| Basic       | 9.5%       | 2,411         | Most stable tier                         |

** Action:** Investigate Pro tier value proposition and onboarding.

### 3. Why Customers Are Leaving (Feedback Mining)
Analyzed **452 churned customers** with verbatim feedback:

**Top Churn Drivers:**
1. **"too expensive"** — 171 mentions
2. **"switched"** (to competitor) — 145 mentions
3. **"missing features"** — 140 mentions

**Other notable themes:** onboarding friction, support quality, integration issues.

### 4. High-Value Customers Churning Early
**Top 10 Churned Customers by MRR** (all Enterprise):

- Several customers with **< 1 month tenure** and **₹17K–₹25K MRR**
- Clear signal of **onboarding failure** or **expectation mismatch** at the highest tier

**Example:** Account `A-118f1c` — ₹25,472 MRR, **0.1 months** tenure, 1 ticket → likely "bought but never activated".


## Visualizations (Tableau)

The notebook exports a clean `master_for_tableau.csv` ready for BI tools. 
** Dashboard Pages:**
1. **Executive Summary** — KPI cards (Total Subscriptions, Churn Rate, Active MRR, ARR at Risk) + visual gauge or color indicator for overall churn rate
2. **Plan Tier Deep Dive** — Churn rate by plan tier (bar chart) + Revenue lost by plan tier (bar chart)
3. **Customer Journey & Retention** — Average tenure months for active vs churned customers (bar chart) — optionally add a tenure bucket bar chart
4. **Behavioral Insights** — Average feature usage by churn status (bar chart) + Average support ticket count by churn status (bar chart)
