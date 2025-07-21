# 🚖 Sprint 5: SQL Data Analysis – Zuber Ride-Sharing Case Study

## 📌 Project Overview
This project demonstrates **SQL-based analytics** using a real-world case for **Zuber**, a ride-sharing startup in Chicago.  
The goal was to explore **passenger preferences**, assess **taxi company performance**, and test the **impact of weather on ride durations**.

---

## ✅ Business Problem
Zuber needs actionable insights to:
- Determine **market trends** and **competition strength**.
- Understand **how external factors (like weather) influence operations**.
- Validate if **ride durations from Loop → O’Hare change during bad weather** on Saturdays.

---

## 📂 Dataset Description
The project utilized **4 relational tables**:

- **`neighborhoods`**: Neighborhood names and IDs  
- **`cabs`**: Cab IDs and associated taxi company names  
- **`trips`**: Trip details (timestamps, duration, distance, pickup/drop-off neighborhoods)  
- **`weather_records`**: Hourly weather observations (temperature, description)  

**Key Challenge:**  
No direct foreign key relationship between `trips` and `weather_records` → joined using timestamps (`start_ts` and `ts`).

---

## ✅ Project Tasks & SQL Queries

### **1. Company Performance Analysis**
**Task:** Find ride counts for each taxi company (Nov 15–16, 2017)  
```sql
SELECT  
    c.company_name,  
    COUNT(*) AS trips_amount  
FROM trips t  
JOIN cabs c ON t.cab_id = c.cab_id  
WHERE DATE(t.start_ts) BETWEEN '2017-11-15' AND '2017-11-16'  
GROUP BY c.company_name  
ORDER BY trips_amount DESC;
```  

Task 2: Number of rides for companies with names containing "Yellow" or "Blue" for Nov 1–7, 2017:

```sql
SELECT  
    c.company_name,  
    COUNT(*) AS trips_amount  
FROM trips t  
JOIN cabs c ON t.cab_id = c.cab_id  
WHERE (c.company_name LIKE '%Yellow%' OR c.company_name LIKE '%Blue%')  
AND DATE(t.start_ts) BETWEEN '2017-11-01' AND '2017-11-07'  
GROUP BY c.company_name  
ORDER BY trips_amount DESC;
```

Aggregate Top Companies vs. Others
Objective: Group top two companies and compare them against all others.

```sql
SELECT  
    CASE  
        WHEN company_name = 'Flash Cab' THEN 'Flash Cab'  
        WHEN company_name = 'Taxi Affiliation Services' THEN 'Taxi Affiliation Services'  
        ELSE 'Other'  
    END AS company,  
    COUNT(trips.trip_id) AS trips_amount  
FROM cabs  
INNER JOIN trips ON trips.cab_id = cabs.cab_id  
WHERE CAST(trips.start_ts AS date) BETWEEN '2017-11-01' AND '2017-11-07'  
GROUP BY company  
ORDER BY trips_amount DESC;
```

Hypothesis Testing: Weather Impact on Ride Duration
Objective: Analyze if bad weather increases ride duration between Loop → O’Hare on Saturdays.

Step 1: Identify neighborhoods:

Loop = neighborhood_id 50

O’Hare = neighborhood_id 63

Step 2: Classify weather as "Good" or "Bad" (rain/storm):

```sql
SELECT  
    DATE_TRUNC('hour', ts) AS ts,  
    CASE  
        WHEN description ILIKE '%rain%' OR description ILIKE '%storm%' THEN 'Bad'  
        ELSE 'Good'  
    END AS weather_conditions  
FROM weather_records;
```

Step 3: Join rides with weather conditions for Saturday trips:

```sql
SELECT  
    start_ts,  
    T.weather_conditions,  
    duration_seconds  
FROM trips  
INNER JOIN (  
    SELECT  
        ts,  
        CASE  
            WHEN description LIKE '%rain%' OR description LIKE '%storm%' THEN 'Bad'  
            ELSE 'Good'  
        END AS weather_conditions  
    FROM weather_records  
) T ON T.ts = trips.start_ts  
WHERE  
    pickup_location_id = 50  
    AND dropoff_location_id = 63  
    AND EXTRACT(DOW FROM trips.start_ts) = 6  
ORDER BY trip_id;
```

## 📊 Key Findings
Top-performing companies: Flash Cab and Taxi Affiliation Services dominated ride counts in November 2017.

Weather impact: Rainy Saturdays showed longer average ride durations for Loop → O’Hare compared to clear weather.

Demand patterns: Highest ride volumes during weekend evenings and peak hours.

## 🛠 Tools & Techniques
Database: PostgreSQL (SQL syntax)

Techniques: Joins, CASE logic, conditional grouping, timestamp filtering, string matching (ILIKE)

Functions used: COUNT(), EXTRACT(), DATE_TRUNC()
