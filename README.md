# 🚕 NYC Taxi Analytics Pipeline — Microsoft Fabric

An end-to-end data engineering pipeline built on Microsoft Fabric processing 3M+ real NYC taxi trips using Medallion Architecture (Bronze/Silver/Gold layers) with PySpark transformations and Power BI dashboard.

## 🚀 Live Dashboard
Built on Microsoft Fabric — nyc-taxi-fabric workspace

## 🏗️ Architecture
Raw NYC Taxi Data (3M+ records)
        ↓
🥉 Bronze Layer — Raw parquet files in Lakehouse
        ↓
🥈 Silver Layer — Cleaned 2.8M valid trips (removed 182K bad records)
        ↓
🥇 Gold Layer — Hourly aggregations (trips, revenue, fare, distance)
        ↓
📊 Power BI Dashboard — Interactive analytics

## ✨ Key Insights from the Data
- Processed 3,066,766 NYC taxi trips from January 2023
- Removed 182,538 bad records (0 passengers, negative fares)
- Peak hour: 1 PM with 168,768 trips
- Highest avg fare: 5 AM at $26.46 (airport runs!)
- Total revenue analyzed: $50M+ across all trips

## 🛠️ Tech Stack
- Microsoft Fabric — unified data platform
- PySpark — distributed data processing
- Lakehouse — unified data storage (Delta format)
- Medallion Architecture — Bronze/Silver/Gold layers
- Power BI — interactive dashboard
- Python — data engineering scripts

## 📁 Project Structure
- 01_bronze_layer.ipynb — Data ingestion and exploration notebook
- README.md — Project documentation

## 💡 How It Works

Step 1 - Bronze Layer
Load raw NYC taxi parquet files into Fabric Lakehouse
Explore schema: 19 columns including pickup/dropoff times, fares, distances

Step 2 - Silver Layer
Filter invalid records (0 passengers, negative fares, zero distance)
Add derived columns: pickup_hour, pickup_day, pickup_month
Result: 2,884,228 clean records saved as Delta table

Step 3 - Gold Layer
Aggregate by pickup hour: total trips, avg fare, avg distance, total revenue
Save as gold_hourly_stats Delta table for Power BI consumption

Step 4 - Power BI Dashboard
Connect via Direct Lake semantic model
4 interactive charts: trips by hour, avg fare, revenue, distance trends

## 📊 Power BI Dashboard Features
- Total Trips by Hour — identify peak demand periods
- Average Fare by Hour — pricing patterns throughout the day
- Total Revenue by Hour — revenue optimization insights
- Average Distance by Hour — trip length trends

## 🎯 What This Demonstrates
- End-to-end data engineering on Microsoft Fabric
- Medallion Architecture implementation
- Large-scale data processing with PySpark (3M+ records)
- Data quality and validation practices
- Business intelligence with Power BI

