# 🏙 Sprint 1: Advanced Spreadsheets – Manhattan Airbnb Analysis

This project analyzed **Airbnb data across NYC neighborhoods** to help identify the most profitable property sizes and locations for vacation rentals.  
The goal was to provide **investment recommendations** by evaluating **neighborhood attractiveness, property size popularity, and potential revenue**.

---

## ✅ Project Objectives
- Determine **which neighborhoods** are most attractive for vacation rentals.
- Identify **the most popular property sizes** (based on number of bedrooms).
- Estimate **annual revenue** for the top-performing listings.

---

## 🔍 Project Features
- **Pivot Tables**: To summarize reviews, property sizes, and revenue by neighborhood.
- **Advanced Formulas**:  
  - `IF()` to clean data (e.g., empty bedrooms → studio)  
  - `SUMIF()` to calculate revenue from the calendar dataset  
  - `VLOOKUP()` for data merging across sheets  
- **Data Cleaning**:
  - Standardized neighborhood names (`neighborhood_clean`)
  - Created clean bedroom column (`bedrooms_clean`)
- **Visualizations**:
  - Bar chart of top 10 neighborhoods by reviews
  - Heatmap for retention of top properties
- **Executive Summary** and **Table of Contents** for stakeholders

---

## 📂 Data & Methodology
- **Listings Sheet**: Neighborhood, bedrooms, and reviews data
- **Calendar Sheet**: Daily availability and adjusted price for 30 days

Steps:
1. **Data Cleaning**:
   - Removed inconsistencies in neighborhood names
   - Replaced null bedroom values with “Studio”
2. **Neighborhood Analysis**:
   - Ranked neighborhoods by **number of reviews in last 12 months**
3. **Property Size Analysis**:
   - Identified top bedroom counts overall and per neighborhood
4. **Revenue Estimation**:
   - Added `revenue_earned` column based on availability and price
   - Summed 30-day revenue and extrapolated annual estimate
5. **Ranking Top Listings**:
   - Filtered top 10 neighborhoods + most popular property size
   - Ranked listings by estimated revenue

---

## 📊 Key Findings
- **Top Neighborhoods**: West Village, Upper East Side, Chelsea, Midtown, East Harlem
- **Most Popular Property Sizes**: Studios, 1-bedroom, and 2-bedroom apartments
- **Revenue Insights**:
  - Highest-earning listing (ID: `49946551`) generated **$29,940 in 30 days**
  - Estimated annual revenue: **$359,280**

---

## 🛠 Tools & Skills Demonstrated
- **Google Sheets / Excel**
- **Pivot Tables** for summarization
- **Formulas**: `IF()`, `SUMIF()`, `VLOOKUP()`, `TEXT()`
- **Data Visualization**: Charts, heatmaps
- **Spreadsheet Organization**: Executive summary, change log, clean formatting

---

## 🔗 View the Full Project
[**Google Sheets Project Link**](https://docs.google.com/spreadsheets/d/1y7Oskxls4ijIkxygr41uNcBJ7DG3d55xMz7udFMt05I/edit?usp=sharing)

