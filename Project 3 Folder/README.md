# 📡 Megaline Telecom Customer Behavior & Revenue Analysis

### 📘 Project Overview

Megaline, a telecom provider, offers two mobile plans — Surf and Ultimate. The commercial team wants to understand which plan performs better, how customers actually use their services, and whether current plan structures align with real‑world behavior.
Using 12 months of customer activity, this project analyzes calls, messages, and internet usage to determine:

_ Which plan generates more revenue

- How customer behavior differs between plans

- Whether users frequently exceed their plan limits

- Whether revenue differs by geographic region

- What Megaline should change to improve profitability and customer satisfaction

This project follows a full analytics workflow: data cleaning, feature engineering, exploratory analysis, revenue modeling, and hypothesis testing.

### 🧰 Data Sources

Five datasets were provided by Megaline:

- users — customer demographics, plan type, registration/churn dates

- plans — monthly allowances and overage rates

- calls — individual call records with duration

- messages — SMS activity

- internet — MB used per session

All datasets were cleaned, validated, and merged into a unified monthly‑level usage table.

### 🛠️ Data Preparation & Feature Engineering

#### ✔️ Cleaning Steps

- Converted date columns to datetime

- Removed zero‑duration calls (19.48% of call records)

- Standardized city names

- Filled missing usage values with zero (representing no activity)

- Ensured no negative or invalid usage values

#### ✔️ Engineered Features

For each user per month:

- Total minutes used

- Total messages sent

- Total MB/GB used

- Extra minutes, messages, and GB beyond plan limits

- Overage charges

- Total monthly revenue (monthly fee + all overages)

### 📊 Behavioral Analysis

#### 📞 Call Usage

- Surf avg: 428.7 min/month

- Ultimate avg: 430.4 min/month

- Max usage across all users: < 1,450 minutes

➡️ Ultimate’s 3,000‑minute allowance is far above actual usage, meaning many Ultimate users could downgrade without losing value.

### 💬 Messaging Behavior

- Surf avg: 31 messages/month

- Ultimate avg: 37 messages/month

#### Top 10% heavy texters:

- Surf: >76 messages

- Ultimate: >83 messages

➡️ Surf’s 50‑message limit is too low for many users, while Ultimate’s 1,000 messages is overly generous.

### 🌐 Internet Usage (Critical Finding)

- Surf avg: 16.17 GB

- Ultimate avg: 16.81 GB

- Surf users exceeding 15GB limit: 57.9%

- Ultimate users exceeding 30GB limit: 5.7%

➡️ Surf users consistently exceed their data allowance, creating high overage revenue but also high churn risk.

### 💵 Revenue Analysis

- Surf avg revenue: $60.71 (high variability)

- Ultimate avg revenue: $72.31 (stable, predictable)

- Surf revenue is driven heavily by overages

- Ultimate revenue is mostly flat monthly fees

➡️ Ultimate generates 26% more revenue per user and is easier to forecast.

➡️ Surf users often pay more than expected due to data overages.

### 🧪 Hypothesis Testing

#### 1️⃣ Revenue Difference Between Plans
- t‑statistic: 5.5689

- p‑value: < 0.0001
  
➡️ Reject H₀ — revenue differs significantly between Surf and Ultimate.

#### 2️⃣ Revenue Difference Between NY‑NJ and Other Regions
- t‑statistic: -2.0194

- p‑value: 0.0436
➡️ Reject H₀ — revenue differs significantly by region.

### 🧭 Conclusions & Business Recommendations

#### 🔍 Key Insights

- Ultimate plan is more profitable and more stable

- Surf plan users frequently exceed data limits

- Actual usage patterns do not align with current plan allowances

- Many Ultimate users could downgrade without losing value

- Surf users may churn due to unexpected overage fees

### 💡 Recommendations

- Increase Surf data allowance (even +1GB would reduce frustration)

- Introduce a mid‑tier plan between Surf and Ultimate

- Reevaluate Ultimate’s excessive call/message allowances

- Target NY‑NJ region with tailored pricing or promotions

- Monitor Surf overage behavior for churn risk

### 🧠 Skills Demonstrated

- Data cleaning & validation

- Feature engineering

- Exploratory data analysis

- Statistical hypothesis testing

- Revenue modeling

- Business insights & recommendations

- Visualization (Matplotlib, Seaborn)

- ### 📁 Project Structure

Project 3 Folder/
- [Project 3.ipynb](https://github.com/BritCoin09/data-portfolio/blob/main/Project%203%20Folder/Project%203.ipynb)
- [README.md](https://github.com/BritCoin09/data-portfolio/blob/main/Project%203%20Folder/README.md)

