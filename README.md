Flight Database SQL Project ✈️
Overview

This project analyzes a real-world flight database using PostgreSQL.
It demonstrates end-to-end SQL skills: importing raw data, cleaning, writing queries, creating views, and extracting insights.

The database is large (~100MB), making it a great simulation of real-world SQL work.

Dataset 📂

The raw flight database (SQL dump) is not stored in this repo because of size (~100 MB).
You can download it from:

Google Drive
- [GitHub Release](https://github.com/0-nirmal0/flight-sql-project/releases/tag/v1.0)  

After downloading, import it into PostgreSQL:
psql -U postgres -d demo -f flight_database.sql

Dataset Details
1. Schema: demo (all tables are created here)
2. Tables: airlines, airports, flights, passengers, etc.
3. Format: .sql dump file imported into PostgreSQL
4. Size: ~100MB

Skills Demonstrated
1. SQL Basics (SELECT, WHERE, ORDER BY, GROUP BY, HAVING)
2. Joins (INNER, LEFT, RIGHT)
3. Aggregations (COUNT, AVG, MAX, MIN, SUM)
4. Views (saved queries for reporting)
5. Subqueries & CTEs (Common Table Expressions)
6. Window Functions (RANK, ROW_NUMBER, PARTITION BY)
7. Data Cleaning using SQL functions

Example Queries

1. Find the top 5 busiest airports:

SELECT airport_id, COUNT(*) AS total_flights
FROM demo.flights
GROUP BY airport_id
ORDER BY total_flights DESC
LIMIT 5;

Repository Structure
flight-sql-project/
│
├── data/                 # (Empty in repo) SQL dump stored in Google Drive
├── scripts/              # SQL query scripts
├── results/              # Any exported results
├── .gitignore
└── README.md             # Project description

How to Run
1. Install PostgreSQL
2. Create a database and schema
CREATE DATABASE demo;
3. Import the .sql file
psql -U postgres -d demo -f flight_database.sql
4. Run queries inside /scripts/ to reproduce insights.

Future Improvements
Add a Power BI dashboard for flight delays.
Export cleaned datasets to CSV for analysis in Excel.


Author
👤 Nirmal Kumar M
GitHub: 0-nirmal0
Skills: SQL | Excel | Power BI | Python (Basics)