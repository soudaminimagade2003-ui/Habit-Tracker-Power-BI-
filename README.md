**🧠 Human Performance Monitoring & Analytics System**
A structured behavioral analytics system designed to transform daily habit tracking data into actionable insights for productivity optimization, burnout detection, and engagement monitoring.

**📌 1. Introduction**

In today’s fast-paced environment, maintaining productivity, emotional stability, and engagement consistency has become challenging. Many individuals and organizations struggle with:

Burnout

Habit inconsistency

Declining motivation

Unmeasured emotional volatility

This project builds a data-driven Human Performance Monitoring System that analyzes habit tracking data to detect:

✅ Productivity Levels

🔥 Burnout Risk

📊 Engagement Patterns

📈 Performance Consistency

The system combines:

A historical simulated dataset (generated using Python)

A live automated habit tracking dataset (via Google Sheets)

A Power BI analytics layer

A Row-Level Security (RLS) implementation

**🎯 2. Problem Statement**

Traditional habit tracking systems only show:

Streak counts

Total completions

Basic summaries

They fail to analyze:

Emotional volatility

Drop-off behavior

Engagement decline patterns

Long-term performance stability

Core Question:

How can daily behavioral data be transformed into meaningful productivity, engagement, and burnout insights using structured analytics?

**🏗️ 3. System Architecture Overview**
Data Source Layer
    ↓
Processing & Automation Layer
    ↓
Analytics Layer (Power BI)
    ↓
Security Layer (RLS)
🔹 Data Source Layer

Python-generated historical dataset

Live habit data via Google Sheets

Validation using Google Apps Script

🔹 Processing Layer

Master Sheet automation

Data consolidation

Duplicate removal

Structured formatting

🔹 Analytics Layer

Power BI dashboards

KPI modeling

Behavioral metrics

Performance analytics

🔹 Security Layer

Row Level Security (RLS)

User-specific dashboard views

**📊 4. Dataset Overview**

This project uses two structured datasets.

A. Historical Dataset (Python Generated)
🎯 Purpose

Created to simulate long-term behavioral data (365 days) for:

Burnout modeling

Productivity tracking

Engagement trend analysis

Behavioral simulation testing

🛠 Data Generation

Programmatically generated using Python with logically structured randomness:

Completion behavior

Mood variation

Time allocation

Habit categories

💾 Storage

Stored in MySQL

Imported into Power BI

🧹 Data Cleaning

Correct data types

Null handling

Created Completion_Flag

Derived AgeGroup column

B. Live Dataset (Google Sheets System)
📥 Data Collection

Each user maintains a personal daily entry sheet in Google Sheets.

✅ Data Validation

Implemented at entry level:

Status dropdown (Done / Missed)

Skip reason dropdown

Date restriction

Numeric time validation

This eliminates:

Spelling errors

Invalid inputs

Format inconsistencies

☁ Storage

Stored in Google Drive (Cloud Folder)

Separate sheets per user

⚙ Automation

Google Apps Script performs:

Sheet merging

Duplicate removal

Structured formatting

Daily automatic updates

🔗 Power BI Integration

Connected to Master Sheet

Live refresh enabled

Automated reporting

**🧩 5. Data Modeling (Power BI)**

The project follows a Star Schema Design for both datasets.

🔹 Historical Dataset Model

Fact Table

Habit Tracking Data

Dimension Tables

User Table

Habit Table

Date Table

Relationships:

User ID

Habit Name

Date Fields

🔹 Live Dataset Model

Fact Table

live_data (Master Sheet)

Dimension Table

all_clients_info_table

Relationships:

Person ID → User Table

Many-to-One relationships

This ensures:

Clean filtering

Accurate aggregation

Optimized performance

**📊 6. Dashboard Insights (Page-Wise)**
🟢 Page 1 – Individual Productivity Dashboard
🎯 Objective

Provide personalized performance tracking.

🔍 Key Features

Personalized Filtering

User Name slicer

Dynamic KPI updates

KPIs

Total Habits

Completed Habits

Skipped Habits

Success Rate %

Failure Rate %

Time Usage

Behavioral Insights

Habit-wise success rate

Skip reason analysis

Date-wise trend

Automated discipline indicator

💡 Core Questions Answered

How productive is the user?

Is performance consistent?

Which habits drive results?

🔵 Page 2 – Overall Performance Dashboard
🎯 Objective

Management-level collective analysis.

🔍 Features

Overall KPIs

Average Completion %

Overall Success Rate

Failure Rate

Total Clients

Active Clients

Comparative Analysis

Top 3 Performers

Habit-wise success across users

Behavioral Patterns

Skip reason matrix

Success vs Failure distribution

🟡 Page 3 – Productivity Analysis Dashboard
🎯 Purpose

Measure performance efficiency and behavioral consistency.

📈 Key Metrics

Completion Rate

Average Mood

Mood Stability (Variation Index)

Total Active Days

📊 Insights

Monthly completion trend

Category-wise time utilization

Top 3 performing habits

Mood trend over time

💡 Solves

Is performance improving?

Is mood aligned with productivity?

Where is time invested most?

🔴 Page 4 – Burnout Analysis Dashboard
🎯 Purpose

Detect early burnout and disengagement signals.

🔍 Key Metrics

Skipping Rate

Partial Completion Rate

Mood Volatility Index

Category-wise skipping

Top 3 skipped habits

Performance distribution (Completed / Partial / Skipped)

🎯 Detects

Avoidance patterns

Emotional instability

Category neglect

Workload stress signals

💡 Core Questions Answered

Is burnout risk increasing?

What are root causes?

Which habits are avoided most?

**🌍 7. Real-Life Use Cases**
🏢 1. Corporate Performance & Employee Well-being

Can help organizations:

Monitor engagement levels

Detect burnout early

Analyze workload stress

Improve employee retention

👤 2. Personal Productivity Monitoring

Goes beyond streaks to analyze:

Emotional stability

Time efficiency

Behavioral drop-offs

Long-term consistency

🎯 3. Coaching & Mentorship Programs

Supports coaches in:

Identifying avoidance behavior

Correlating mood with performance

Designing habit restructuring plans

🎓 4. Academic & Student Productivity Tracking

Useful for institutions to:

Monitor study consistency

Detect stress-related decline

Support academic counseling

🔐 Security Implementation

Row Level Security (RLS)

User-specific data access

Controlled visibility

🚀 Technologies Used

Python (Data Simulation)

MySQL (Data Storage)

Google Sheets (Live Tracking)

Google Apps Script (Automation)

Power BI (Analytics & Visualization)

📌 Conclusion

This project transforms simple habit tracking into a structured behavioral intelligence system.

Instead of merely counting completed tasks, it:

Detects productivity trends

Identifies burnout risk

Analyzes emotional consistency

Converts raw data into actionable insights

It demonstrates how analytics can bridge the gap between data and human performance improvement.
