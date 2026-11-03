# Customer Lifetime Value (CLV) & RFM Segmentation Analysis

An end-to-end e-commerce customer analytics project integrating **Customer Lifetime Value (CLV)** modelling with **Recency, Frequency, Monetary (RFM)** segmentation to drive targeted marketing strategies and maximize customer profitability. Results and insights are visualized in an interactive **Tableau Dashboard**.

---

## Project Overview & Objectives

* **Project Objective:** Analyze historical transaction records to segment customers based on purchasing behavior (RFM) and compare actual **Historical CLV (Profit)** against **Predictive CLV (Forecasting)**.
* **Dataset Scope:** 100 unique customers across 571 transactions (`2024-01-04` to `2026-09-15`).
* **Deliverable:** Interactive Tableau Dashboard visualizing monthly CLV trends, actual vs. predicted CLV performance, segment distributions, and transaction volume vs. Average Order Value (AOV).

---

## Analytical Framework & Methodology

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                       CLV & RFM ANALYTICAL PIPELINE                         │
├──────────────────────────────┬──────────────────────────────┬───────────────┤
│    1. Historical CLV         │     2. Predictive CLV        │  3. RFM       │
│                               │                              │  Segmentation │
│  • Historical Revenue        │  • Annual Churn Rate: 40%    │  • Recency    │
│  • Gross Margin: 30%         │  • Retention Rate: 60%       │  • Frequency  │
│  • Historical CLV =          │  • Discount Rate: 10%        │  • Monetary   │
│    Revenue × 30% Gross Margin│  • Discounted CLV Model      │  • 1–5 Scoring│
└──────────────────────────────┴──────────────────────────────┴───────────────┘
```

### 1. Historical CLV Calculation
Calculates the actual profit realized from each customer to date:
$$\text{Historical CLV} = \text{Total Revenue} \times \text{Gross Margin (30\%)}$$

### 2. Predictive CLV Model
Forecasts future value based on purchase frequency, AOV, and churn assumptions:
$$\text{Expected Lifespan} = \frac{1}{\text{Churn Rate (40\%)}} = 2.5 \text{ years}$$
$$\text{Discount Factor} = \frac{r}{1 + d - r} = \frac{0.60}{1 + 0.10 - 0.60} = 1.20$$
$$\text{Predictive CLV} = \text{Annual Margin} \times \text{Discount Factor}$$

### 3. RFM Scoring & Segmentation
Customers are scored from **1 to 5** across three dimensions using quintiles:
* **Recency (R):** Days since last purchase (Score 5 = 5–35 days; Score 1 = $\ge$774 days)
* **Frequency (F):** Total order count (Score 5 = $\ge$19 orders; Score 1 = 1–2 orders)
* **Monetary (M):** Total monetary spend in IDR (Score 5 = $\ge$IDR 4,269,000; Score 1 = IDR 1–238,000)

---

## Executive Dashboard Summary (Tableau Output)

| Metric | Total Value | Notes / Baseline |
| :--- | :---: | :--- |
| **Total Customers** | **100** | Active customer database |
| **Total Transactions** | **571** | Complete transaction log |
| **Historical CLV (Profit)** | **Rp 110,892,000** | Realized cumulative profit (30% margin) |
| **Predictive CLV** | **Rp 89,455,394** | Discounted projected future CLV |

---

## Key Business Insights

### 1. New Customer CLV Underperformance
* **Finding:** The **New Customers** segment is the **only segment** that has not yet met its predictive CLV benchmark (Historical CLV of **Rp 3,510,823** vs higher predictive target).
* **Strategic Implication:** Early drop-off or low second-purchase rate is capping revenue before new users reach their calculated potential.

### 2. The Pareto Principle in Customer Profitability (36% $\to$ 80%)
* **Finding:** Although **Promising**, **Loyal**, and **Champions** represent only **~36% of total customers** (36 out of 100), they contribute approximately **80% of total Historical CLV** (~Rp 69.35M of Rp 110.89M total profit).
* **Breakdown:**
  * **Promising:** Rp 29,300,532 (25 customers)
  * **Champions:** Rp 21,044,865 (5 customers)
  * **Loyal:** Rp 19,009,999 (6 customers)

### 3. High-Value Niche: The 'Need Attention' Segment
* **Finding:** The **Need Attention** segment boasts the highest Average Order Value (**AOV ~IDR 1,057,222**), generated from **54 transactions across just 4 customers** (Total Monetary Rp 57,090,000).
* **Strategic Implication:** These high-spending buyers purchase premium, high-yielding products but show declining transaction frequency.

---

## Recommendations

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         STRATEGIC ACTION MATRIX                             │
├───────────────────┬─────────────────────────────────────────────────────────┤
│ Customer Segment  │ Strategic Action & Tactics                              │
├───────────────────┼─────────────────────────────────────────────────────────┤
│ New Customers     │ • Educate on product usage & onboarding sequences        │
│                   │ • Gamify experience with sign-up bonus points            │
│                   │ • Cross-sell complementary starter products             │
├───────────────────┼─────────────────────────────────────────────────────────┤
│ Champions         │ • Dedicated VIP customer support & relationship mgmt    │
│ (Pareto Core)     │ • Exclusive early access to premium product launches    │
├───────────────────┼─────────────────────────────────────────────────────────┤
│ Promising         │ • Turn into brand advocates via affiliate programs     │
│ (Pareto Core)     │ • Offer community badges & referral coupons             │
│                   │ • Reward product reviews with discount vouchers          │
├───────────────────┼─────────────────────────────────────────────────────────┤
│ Loyal             │ • Targeted retargeting campaigns (re-engage inactive)   │
│ (Pareto Core)     │ • Personalized product recommendations based on history  │
├───────────────────┼─────────────────────────────────────────────────────────┤
│ Need Attention    │ • Multi-channel retargeting (Meta Ads, Google Ads)      │
│ (High AOV Niche)  │ • Showcase new inventory arrivals & high-end collections│
└───────────────────┴─────────────────────────────────────────────────────────┘
```

### 1. Optimize Revenue Gain from New Customers
* **Goal:** Bridge the gap between actual and predictive CLV.
* **Actionable Steps:**
  * Implement automated onboarding email/WhatsApp sequences educating new users on product usage.
  * Introduce gamification elements (e.g., bonus points upon completing a second order within 30 days).
  * Bundle entry-level items to increase initial order basket value.

### 2. Protect & Nurture Pareto Segments (36% Yielding 80% Revenue)
* **Champions:**
  * Provide white-glove customer support and direct account management.
  * Solicit product feedback to reinforce brand loyalty.
* **Promising:**
  * Mobilize as brand advocates/affiliates.
  * Award community badges and exclusive discount coupons for referring new users or posting verified reviews.
* **Loyal:**
  * Deploy automated win-back and retargeting ads, as many members have not purchased recently despite high lifetime frequency.

### 3. Re-engage the 'Need Attention' High-Yield Segment
* **Goal:** Capitalize on high purchasing power (~IDR 1M AOV).
* **Actionable Steps:**
  * Launch dynamic retargeting campaigns across **Meta Ads** and **Google Display Network**.
  * Highlight new premium arrivals and limited-edition product drops to trigger high-value repeat orders.

---
