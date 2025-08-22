# Flight Database SQL Project ✈️

## Overview  
This project analyzes a real-world **flight database** using PostgreSQL.  
It demonstrates **end-to-end SQL skills**: importing raw data, cleaning, writing queries, creating views, and extracting insights.  

The database is large (~100MB), making it a great simulation of real-world SQL work.  

---

## Dataset  
- **Source**: Flight database (contains tables like `airlines`, `airports`, `flights`, `passengers`)  
- **Format**: `.sql` file imported into PostgreSQL  
- **Size**: ~100MB  

---

## Skills Demonstrated  
- SQL Basics (**SELECT, WHERE, ORDER BY, GROUP BY, HAVING**)  
- **Joins** (INNER, LEFT, RIGHT)  
- **Aggregations** (COUNT, AVG, MAX, MIN, SUM)  
- **Views** (saved queries for reporting)  
- **Subqueries & CTEs** (Common Table Expressions)  
- **Window Functions** (RANK, ROW_NUMBER, PARTITION BY)  
- Data Cleaning using SQL functions  

---

## Example Queries  

**1. Find the top 5 busiest airports:**  

SELECT airport_id, COUNT(*) AS total_flights
FROM flights
GROUP BY airport_id
ORDER BY total_flights DESC
LIMIT 5;

**2. Find the most popular airline by passenger count:**

SELECT a.airline_name, COUNT(f.flight_id) AS total_passengers
FROM airlines a
JOIN flights f ON a.airline_id = f.airline_id
GROUP BY a.airline_name
ORDER BY total_passengers DESC
LIMIT 1;


**3. Create a view for on-time performance:**

CREATE VIEW on_time_performance AS
SELECT airline_id,
       COUNT(*) FILTER (WHERE delay_minutes = 0) AS on_time_flights,
       COUNT(*) AS total_flights,
       ROUND((COUNT(*) FILTER (WHERE delay_minutes = 0)::decimal / COUNT(*)) * 100, 2) AS on_time_percentage
FROM flights
GROUP BY airline_id;


## Repository Structure

flight-sql-project/
│
├── data/                 # Raw flight database .sql file
├── queries/              # SQL query scripts
│   ├── joins.sql
│   ├── views.sql
│   └── analysis.sql
├── docs/                 # Notes or ER diagrams
└── README.md             # Project description

## How to Run

**1. Install PostgreSQL.**
**2.Create a database:**
CREATE DATABASE flightdb;

**3.Import the .sql file:**
psql -U postgres -d flightdb -f data/flight_database.sql

**4.Run the queries inside /queries/ to reproduce insights.**

## Future Improvements

**Add a Power BI dashboard for flight delays.**
**Export cleaned datasets to CSV for analysis in Excel.**

## Author

👤 Nirmal Kumar M

GitHub: 0-nirmal0

Skills: SQL | Excel | Power BI | Python (Basics)


