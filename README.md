# 🚕 NYC Taxi Analytics Pipeline — Microsoft Fabric

An automated end-to-end data engineering pipeline built on Microsoft Fabric processing 3.7M+ real NYC taxi trips using Medallion Architecture (Bronze/Silver/Gold layers) with monthly automated ingestion, PySpark transformations, and Power BI dashboard.

## 🚀 Live Dashboard
Built on Microsoft Fabric — nyc-taxi-fabric workspace

## 🏗️ Architecture
NYC Taxi Data (auto-downloaded monthly) → Bronze Layer (raw parquet files) → Silver Layer (cleaned 2.5M valid trips) → Gold Layer (hourly aggregations) → Power BI Dashboard (interactive analytics)

## ✨ Key Features
- Fully automated monthly pipeline via Microsoft Fabric Data Factory
- Auto-detects and downloads latest NYC taxi data every month
- PySpark data cleaning removing 1.17M+ invalid records
- Medallion Architecture following industry standard (Bronze/Silver/Gold)
- Power BI dashboard with 4 interactive charts
- Runs entirely on Microsoft Fabric cloud platform

## 📊 Key Insights from January 2026 Data
- Processed 3,724,889 real NYC taxi trips
- Removed 1,173,038 bad records (invalid fares, zero passengers, zero distance)
- Peak hour: 6 PM with 185,223 trips
- Highest avg fare: 5 AM at $29.09 (airport runs!)
- Total revenue analyzed: $80M+ across all trips

## 🛠️ Tech Stack
- Microsoft Fabric — unified data platform
- PySpark — distributed data processing at scale
- Lakehouse — unified data storage in Delta format
- Data Factory — automated monthly pipeline orchestration
- Medallion Architecture — Bronze/Silver/Gold layers
- Power BI — interactive analytics dashboard
- Python — data engineering scripts

## 📁 Project Structure
- 01_bronze_layer.ipynb — Full pipeline notebook (Bronze + Silver + Gold layers)
- README.md — Project documentation

## ⚙️ How It Works

Step 1 — Auto Data Ingestion
Data Factory triggers the notebook monthly on a schedule.
Notebook automatically detects the latest available NYC taxi month.
Downloads parquet file (60MB+) directly to Fabric Lakehouse Files.

Step 2 — Bronze Layer
Raw parquet file stored in Lakehouse Files.
Schema exploration and row count validation performed.

Step 3 — Silver Layer
Standardize all column names to lowercase.
Filter invalid records: 0 passengers, negative fares, zero distance.
Add derived columns: pickup_hour, pickup_day, pickup_month.
Save as Delta table: silver_taxi_trips.

Step 4 — Gold Layer
Aggregate by pickup hour: total trips, avg fare, avg distance, total revenue.
Save as Delta table: gold_hourly_stats for Power BI consumption.

Step 5 — Power BI Dashboard
Connect via Direct Lake semantic model for real-time data access.
4 interactive charts showing trips, fares, revenue, and distance trends.

## 📈 Power BI Dashboard Features
- Total Trips by Hour — identify peak demand periods
- Average Fare by Hour — pricing patterns throughout the day
- Total Revenue by Hour — revenue optimization insights
- Average Distance by Hour — trip length trends by time of day

## 🎯 What This Demonstrates
- Fully automated end-to-end data engineering on Microsoft Fabric
- Medallion Architecture implementation (industry standard at top companies)
- Large-scale data processing with PySpark (3.7M+ records)
- Automated monthly pipeline orchestration with Data Factory
- Data quality validation and cleaning practices
- Business intelligence with Power BI Direct Lake connection

