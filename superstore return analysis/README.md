# 📊 Sprint 5: Storytelling with Data – Superstore Returns Analysis

## 📌 Project Overview
This project focused on applying **data storytelling principles** using **Tableau** to analyze the root causes of product returns at **Superstore**.  
The objective was to identify **factors driving returns**, design an **interactive dashboard**, and create a **narrative-driven presentation** for executive decision-making.

---

## ✅ Business Objective
The **Superstore CEO** wants to understand:
- Why are so many orders being returned?
- Are there patterns by product category, region, or time?
- What actionable steps can reduce return rates and associated losses?

---

## 📂 Dataset
The analysis used **Superstore.xls**, which includes:
- **Orders Table**: Product details, sales, and returns.
- **Returns Table**: Return status for each order.

**Key Data Preparation:**
- **LEFT JOIN**: Combined Orders with Returns table.
- Created **calculated field** for `Returned`:
  - Yes → 1  
  - Null → 0  
- Return Rate = `AVG(Returned)`.

---

## ✅ Key Analysis & Visualizations
### **Part 1: Root Cause Analysis**
Created multiple worksheets in Tableau:
- **Scatterplot**: Correlation between **Total Sales** vs. **Total Returns** (by Subcategory).
- **Bar Chart**: Return Rate by **Product Category**.
- **Customer View**: Return Rate by Customer (filtered for customers with >1 order).
- **Map Visualization**: Geographic concentration of returns (State-level).
- **Time Analysis**: Return Rate by Month (seasonal trends).
- **Composite Charts**: Combined views (e.g., Date + Geography + Category).

**Insights:**
- Furniture and Technology categories showed higher return rates.
- Certain states had disproportionately high return activity.
- Some customers exhibited repeated return behavior.
- Seasonal spikes suggested timing effects on returns.

---

### **Part 2: Dashboard Design**
- Created **low-fidelity mockups** (3 sketches).
- Selected best layout for Tableau dashboard.
- Dashboard included:
  - KPIs: Total Returns, Return Rate.
  - Interactive filters for **Region, Category, Date**.
  - Visual summaries of return drivers.

---

### **Part 3: Storytelling with Data**
- Built a **Tableau Story** summarizing:
  - Key findings and root causes.
  - Explanation of return metrics (rate vs. count vs. cost).
  - Dashboard walkthrough for executives.
- Delivered a **3-5 minute presentation** explaining:
  - How to interpret visuals.
  - How to apply filters to identify patterns.
  - Recommendations for reducing returns.

---

## 📊 Tools & Techniques
- **Tool:** Tableau
- **Skills Demonstrated:**
  - Data preparation (joins, calculated fields).
  - KPI design and composite visualizations.
  - Dashboard layout planning and interactivity.
  - Storytelling with data-driven narratives.

---

## 📈 Key Recommendations
1. **Product Policy**: Focus on high-return categories (Furniture, Technology).
2. **Geographic Strategy**: Investigate states with excessive returns.
3. **Customer Management**: Flag repeat return customers for follow-up.
4. **Seasonal Planning**: Adjust inventory and marketing during high-return periods.

---

## 🔗 Tableau Dashboard
View the interactive dashboard on Tableau Public:  
**[👉 Click Here to View](https://public.tableau.com/views/sprint5project_17440434849770/Story1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)


