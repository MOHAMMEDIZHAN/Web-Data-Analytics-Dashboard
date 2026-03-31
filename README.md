# 📊 Web Data Analytics Dashboard – Power BI

## 📌 Project Overview

This project presents an **interactive Power BI dashboard** developed to analyze one month of web analytics data for a consulting company. The dashboard provides insights into website performance, user behavior, engagement metrics, and bot traffic patterns.

The solution is designed using **data modeling, DAX calculations, and interactive visualizations** to support data-driven decision-making and operational monitoring.

The dataset used in this project contains **53,900+ records** collected between **February 28, 2026, and March 28, 2026**.

---

## 🎯 Project Objectives

* Analyze website performance using key performance indicators (KPIs)
* Identify user engagement trends and high-performing pages
* Detect and quantify bot traffic activity
* Provide additional behavioral insights for decision-making
* Enable dynamic filtering using date and week-based slicers

---

## 📂 Dataset Description

The project uses the following datasets:

| Dataset Name    | Description                                             |
| --------------- | ------------------------------------------------------- |
| **Visitor**     | Stores unique user identities                           |
| **Session**     | Represents individual website visits                    |
| **Event**       | Captures user actions (clicks, page views, conversions) |
| **BotSignal**   | Contains bot detection scores                           |
| **SessionPath** | Tracks user navigation paths                            |
| **Metadata**    | Defines relationships between datasets                  |

### Dataset Summary

* Total Records: **53,900+**
* Time Period: **Feb 28 – Mar 28, 2026**
* Data Type: Web Analytics / User Behavior Data

---

## 🧠 Data Modeling

A relational data model was implemented to ensure accurate filtering and aggregation.

### Relationships

```
Visitor (1) ────< Session (Many)

Session (1) ────< Event (Many)

Session (1) ────< BotSignal (Many)

Session (1) ────< SessionPath (Many)

Date Table (1) ────< Session (Many)
```

### Key Data Preparation Steps

* Converted timestamps to Date/Time format
* Created **Session Date** column
* Built a custom **Date Table**
* Established one-to-many relationships
* Validated data integrity

---

## 🛠 Tools and Technologies Used

* **Power BI Desktop**
* **DAX (Data Analysis Expressions)**
* **Data Modeling**
* **Data Visualization**
* **Business Intelligence**
* **Data Cleaning & Transformation**

---

## 📊 Dashboard Structure

The dashboard consists of **three pages**.

---

# 📄 Part 1 – Website KPI Dashboard

This page provides an overview of website performance metrics.

## Key Metrics

* Total Sessions
* Total Unique Visitors
* Total Events
* Average Session Duration
* Sessions per Visitor
* Events per Session

## Visualizations

* KPI Cards
* Top 10 Landing Pages (Bar Chart)
* Top 10 Most Viewed Pages (Bar Chart)
* Date Range Slicer
* Week Slicer

## Purpose

* Monitor website performance
* Identify high-traffic pages
* Track engagement metrics

---

# 🤖 Part 2 – Bot Traffic & Daily Trend Analysis

This page focuses on identifying automated traffic and analyzing session trends.

## Bot Classification Logic

```
If bot score < 50 → Human

If bot score ≥ 75 → Bot
```

## Key Metrics

* Total Bots
* Total Humans
* Bot Percentage
* Daily Sessions Trend

## Visualizations

* Donut Chart – Bot vs Human Distribution
* Line Chart – Daily Sessions Trend
* KPI Cards – Bot Metrics

## Purpose

* Detect automated traffic
* Monitor traffic quality
* Identify unusual activity

---

# 📈 Part 3 – Additional Key Insights

This page provides deeper behavioral and engagement insights.

---

## 1️⃣ Avg Session Duration by Landing Page

### Objective

Identify which pages retain users the longest.

### Visual

Bar Chart

### Insight

High session duration indicates strong user engagement and valuable content.

---

## 2️⃣ Bot Percentage by Bot Type

### Objective

Measure the proportion of bot traffic.

### Visual

Donut Chart

### Insight

Helps evaluate traffic quality and detect automated activity.

---

## 3️⃣ New Visitors vs Returning Visitors

### Objective

Analyze user retention and repeat visits.

### Visual

Donut Chart

### Insight

Measures customer loyalty and engagement.

---

## 4️⃣ Total Sessions by Day of Week

### Objective

Identify peak usage patterns.

### Visual

Column Chart

### Insight

Supports operational planning and marketing timing.

---

## 📊 Key DAX Calculations

### Total Sessions

```DAX
Total Sessions =
COUNT('Session'[id])
```

### Total Visitors

```DAX
Total Visitors =
DISTINCTCOUNT('Visitor'[id])
```

### Total Events

```DAX
Total Events =
COUNT('Event'[id])
```

### Average Session Duration

```DAX
Avg Session Duration =
AVERAGE('Session'[Session Duration (seconds)])
```

### Sessions per Visitor

```DAX
Sessions per Visitor =
DIVIDE(
    [Total Sessions],
    [Total Visitors]
)
```

### Events per Session

```DAX
Events per Session =
DIVIDE(
    [Total Events],
    [Total Sessions]
)
```

### Bot Type

```DAX
Bot Type =
SWITCH(
    TRUE(),
    'BotSignal'[score] < 50, "Human",
    'BotSignal'[score] >= 75, "Bot",
    "Suspicious"
)
```

---

## 🔍 Key Insights Generated

* Identified high-performing landing pages with strong engagement
* Detected significant bot traffic affecting analytics accuracy
* Observed peak traffic patterns during weekdays
* Measured visitor retention using returning visitor analysis
* Enabled dynamic time-based performance monitoring

---

## 🚀 Features

* Interactive dashboard
* Dynamic filtering using slicers
* Automated KPI calculations
* Real-time trend analysis
* User behavior insights
* Bot detection analysis
* Clean and professional UI design

---

## 📦 How to Use This Project

1. Download the `.pbix` file
2. Open in **Power BI Desktop**
3. Explore the dashboard pages
4. Use slicers to filter data
5. Analyze trends and insights

---

## 📸 Screenshots

```
screenshots/
    part1_dashboard.png
    part2_dashboard.png
    part3_dashboard.png
```

---

## 📌 Project Highlights (Resume Ready)

* Built a **3-page Power BI dashboard** analyzing **53,900+ web records**
* Implemented relational data modeling and advanced DAX calculations
* Designed interactive visualizations for performance monitoring
* Generated actionable insights on user engagement and traffic quality

---

## 👨‍💻 Author

**K. Mohammed Izhan**
B.Tech Computer Science and Engineering
Data Analytics | Business Intelligence | Power BI
