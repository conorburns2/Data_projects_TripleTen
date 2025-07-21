# Business Analytics Project – E-Commerce Conversion Funnel & Cohort Analysis

## 📌 Project Overview
This project was part of **Sprint 3: Business Analytics** in my bootcamp. The objective was to analyze **user activity logs** from an e-commerce company and transform them into actionable business metrics. The analysis focused on **conversion funnel creation**, **cohort-based retention analysis**, and calculating **retention rates** using spreadsheet tools and advanced formulas.

---

## 🏢 Business Problem
The executive team wants insights into:
- **Conversion performance**: How effectively does the website convert product page views into purchases?
- **Customer retention**: How engaged are customers after their first purchase, and how does retention change over time?

Your role as a **junior analyst**:
- Build a **conversion funnel** to evaluate user progression from product views to purchases.
- Conduct **cohort analysis** to calculate retention rates month-over-month.
- Prepare a polished **executive summary** for decision-makers.

---

## 📂 Dataset Description
The dataset provided was in a Google Spreadsheet under the `raw_user_activity` tab. Each row represents an **event** (page view, cart open, or purchase) performed by a user.

### **Columns:**
- `user_id` – Unique customer ID
- `event_type` – Type of activity (view, cart, purchase)
- `category_code` – Product category
- `brand` – Brand name
- `price` – Price of the product (USD)
- `event_date` – Date of the activity (YYYY-MM-DD)

---

## ✅ Project Steps

### **Part 1: Build a Conversion Funnel**
- Created a pivot table to calculate **unique users** at each stage:
  - **Product Page View → Add to Cart → Purchase**
- Added:
  - **Total Conversion Rate** (View → Purchase)
  - **Step-by-Step Conversion Rate** (e.g., View → Cart, Cart → Purchase)

---

### **Part 2: Prepare Data for Cohort Analysis**
- Filtered `purchase` events into a new sheet (`purchase_activity`).
- Calculated **first purchase date** for each user using **VLOOKUP** and pivot tables.
- Created:
  - `event_month`
  - `first_purchase_month`
  - `cohort_age` (in months)

---

### **Part 3: Calculate Retention Rates**
- Built a **cohort analysis pivot table** by grouping users into cohorts based on their first purchase month.
- Tracked unique users by **cohort age** (0–4 months).
- Created a `retention_rates` sheet to calculate retention as a percentage of the cohort's starting size.

---

### **Part 4: Organize & Document**
- Added:
  - **Executive Summary** (conversion results, retention insights, assumptions)
  - **Table of Contents** for easy navigation
- Applied best practices:
  - Freeze headers, format numbers/dates, add borders
  - Organized sheets: Summary → Analysis → Calculations → Raw Data

---

## 📈 Key Deliverables
- **Conversion Funnel Sheet**:
  - Funnel visualization with conversion rates
- **Cohort Analysis Sheet**:
  - Retention metrics for 6 acquisition cohorts
- **Executive Summary**:
  - Business insights and recommendations

---

## 🛠 Tools & Techniques
- **Spreadsheet Tools**: Google Sheets / Excel
- **Formulas Used**: `VLOOKUP()`, `TEXT()`, `DATEDIF()`, retention calculations
- **Data Analysis**: Pivot tables, advanced filtering, cohort modeling

---

## 💡 Key Insights
- Identified **conversion drop-offs** between product views and cart additions.
- Calculated **overall conversion rate** for the site.
- Found **retention patterns** across cohorts and determined engagement declines after Month 2.

[See Google Sheets Here](https://docs.google.com/document/d/1sr9yFXf0BmSmmTS-p638Mxe4yvmBhKCq2RwzmomtaGg/edit?usp=sharing)
