# 📊 Sprint 6: Shopify App Analysis – Power BI Dashboard

## 📌 Project Overview
This project involved building an **interactive Power BI report** to analyze publicly available Shopify App Store data.  
The goal was to identify **key factors influencing app success**, including **review patterns**, **developer responsiveness**, and **category distribution**.

---

## ✅ Business Objective
As a BI analyst, the task was to:
1. Understand the **app landscape** (app counts, review activity, ratings).
2. Analyze **review quality** and developer responsiveness.
3. Identify **top developers** based on ratings and responsiveness.
4. Provide actionable insights to optimize app performance on Shopify.

---

## 📂 Dataset Description
The dataset **`shopify.xlsx`** contained four tables:
- **apps**: App details including name, developer, rating, and last modification date.
- **apps_categories**: Mapping table between apps and categories.
- **categories**: App categories and descriptions.
- **reviews**: User reviews with ratings, helpful votes, and developer replies.

---

## ✅ Key Analysis & Power BI Pages

### **1. App Landscape**
- **KPIs**:
  - Total number of apps (Unique count).
- **Line Chart**:
  - Review count trend over time (`lastmod` on X-axis, review count on Y-axis).
- **Scatterplot**:
  - Relationship between **reviews_count (X)** and **average rating (Y)**.
  - Annotated insights using Text Boxes.

---

### **2. Reviews Analysis**
- Created **calculated column** `helpful_reviews` using DAX:  

helpful_reviews = rating * (1 + helpful_count)

diff
Copy
Edit
- Displayed average helpful review score in a KPI Card.
- Created **developer_answered** column using DAX:  
developer_answered = IF(ISBLANK(developer_reply), 0, 1)

yaml
Copy
Edit
- Scatterplot comparing **average rating by developer responsiveness**.

---

### **3. App Reviews & Developer Performance**
- Built **relationships** between `reviews` and `apps` tables (`app_id` → `id`).
- **Bar Charts**:
- Developer vs. sum of ratings.
- Developer vs. average helpful_reviews (more accurate than raw sum).
- Developer responsiveness chart filtered for apps with `reviews_count > 500`.

---

## 📊 Tools & Techniques
- **Power BI**:
- Data Modeling (relationships, cardinality)
- DAX (calculated columns, measures)
- Interactive visualizations and filtering
- **Skills Demonstrated**:
- KPI Cards
- Line and scatter plots
- Bar charts with conditional filters
- Insight annotations for stakeholders

---

## 📈 Key Insights
- **High-rated apps** often have **consistent developer engagement** (prompt responses to user reviews).
- Apps with **higher helpful review scores** correlate with strong user trust and retention.
- **Review trends** indicate seasonal activity spikes, suggesting optimal timing for feature updates.

---

## 🔗 Project Deliverables
- **Power BI Report** (.pbix file not shared due to size limitations).
- **Screenshots**: All visuals for each section (App Landscape, Reviews, App Reviews).
