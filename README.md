**1. Introduction to the Project**
In today’s fast-paced environment, maintaining personal productivity, emotional stability, and consistent engagement has become challenging. Many individuals struggle with burnout, inconsistency in habits, and declining motivation.
This project focuses on building a Human Performance Monitoring & Analytics System that analyzes habit data to detect:
•	Productivity levels
•	Burnout risk
•	Engagement patterns
•	Performance consistency
The system combines:
•	A historical simulated dataset (created using Python for advanced analytical modeling)
•	A live habit tracking dataset (collected through Google Sheets automation)
Using Power BI, the system transforms raw behavioral data into meaningful insights that can support individuals, teams, and organizations.


**2. Problem Statement**
Modern organizations and individuals face difficulty in:
•	Measuring real productivity
•	Identifying early signs of burnout
•	Tracking engagement consistency
•	Converting daily habit data into actionable insights
Most habit tracking systems only show basic statistics such as total completion or streaks. They do not provide deeper behavioral analysis like emotional volatility, drop-off patterns, or engagement risk & for over the time analysis 
Therefore, the problem addressed in this project is:
How can we design a structured analytics system that transforms daily habit tracking data into meaningful insights such as productivity optimization, burnout detection, and engagement tracking?


**3.Project Overview **
Data Source Layer: Uses Python-generated data and Google Sheets for real-time tracking, validated via Google Apps Script.
                                              ⬇️
Processing Layer: Centralizes data validation and automation using a Master Google Sheet and Apps Script.
                                              ⬇️
Analytics Layer: Employs Power BI to create productivity and burnout dashboards from the processed data.
                                              ⬇️
Security Layer: Implements Row Level Security (RLS) to ensure user-specific data views.


4. Dataset Overview
This project uses two different datasets.
A. Historical Dataset (Python Generated)
	Purpose of This Dataset
       Since live data was limited, the historical dataset was created to:
•	Perform burnout modeling
•	Calculate productivity over the period of 365
•	Analyze engagement patterns
•	Test behavioral analytics logic
	Data Collection
Generated programmatically using Python.
Random but logically structured values were assigned for:
•	Completion behavior
•	Mood variation
•	Time allocation
•	Habit categories
This allowed simulation of real-world behavioral patterns.
	Data Storage  Stored in MYSQL and imported into Power BI.

	Data Cleaning 
Cleaning steps included:
•	Ensuring correct data types
•	Handling null values
•	Creating calculated flags (Completion_Flag)
•	Creating derived columns (AgeGroup)

B. Live Dataset (Google Sheets System)
         Data Collection Method  Tool Used: Google Sheets  Each user maintains their own daily entry sheet.
	Data Validation
To ensure data quality:
•	Status dropdown (Done / Missed only)
•	Skip reason dropdown
•	Date format restriction
•	Time restricted to numeric values
This eliminated:
•	Spelling errors
•	Invalid entries
•	Inconsistent formatting
Data quality was controlled at entry level.


	Data Storage
All sheets were stored in: Google Drive (Cloud Folder) Each user had separate input sheets.
	Automation
Google Apps Script was implemented to:
•	Merge all individual sheets
•	Remove duplicates
•	Maintain structured format
•	Update Master Sheet automatically
The script runs on a daily time trigger. So the system works automatically without manual consolidation.
	Power BI Integration
Power BI is connected directly to the Master Sheet.
This enables:
•	Live data refresh
•	Real-time dashboard updates
•	Automated reporting


**5. Data Modeling**

The project follows a structured data modeling approach in Power BI.
1.For Python Generated Dataset- 

 A. Star Schema Design
The model consists of:
Dimension Tables:
•	User Table
•	Habit Table
•	Date Table (derived using week start date)
Relationships were created using:
•	User ID
•	Habit Name
•	Date fields
This ensures proper filtering and aggregation.

For Live Dataset - 
 
A. Star Schema Design
The model was designed using a Star Schema approach to ensure clean filtering, accurate aggregation, and better performance in Power BI.
Fact Table:  live_data Table (Master Sheet Data)
Dimension Tables:   all_clients_info_table
Relationships  Were Created Using Person ID → User Table
All relationships were: • Many-to-one


**6. Insights – Page Wise Explanation**

**Page 1: Individual Productivity Analysis Dashboard**
1. Motive of the Page
The primary objective of this page is to provide personalized performance tracking for each individual user.
This dashboard is designed to:
•	Monitor daily habit completion
•	Track time utilization
•	Measure success and failure rates
•	Identify skip reasons
•	Provide motivational performance insights
The page is user-specific and dynamically updates based on the User Name slicer, ensuring each individual can view only their own performance data.
2. Solution Provided by This Page
This page solves the above problems by:
 Personalized Filtering
•	A User Name slicer allows selecting a specific individual.
•	All KPIs and visuals dynamically update based on the selected user.
 KPI Monitoring
Displays key performance indicators such as:
•	Total Habits
•	Completed Habits
•	Skipped Habits
•	Success Rate %
•	Failure Rate %
•	Time Usage
Habit-Level Analysis
•	Habit-wise time usage
•	Habit-wise success rate
•	Habit-wise completion flags
Behavioral Insights
•	Skip reason analysis
•	Date-wise success vs failure trend
•	Automated insight message (discipline indicator)

**Page 2: Overall Performance Analysis Dashboard**
1. Motive of the Page
The purpose of this page is to analyze the collective performance of all users in the system.
2. Solution Provided by This Page
Unlike Page 1 (individual view), this page provides a management-level overview of overall productivity trends.
This page provides a consolidated analytical view including:
 Overall KPIs
•	Average Client Completion %
•	Overall Success Rate %
•	Failure Rate %
•	Total Clients
•	Active Clients
 Performance Trends
•	Period-wise success rate tracking
•	Date-based performance movement
Comparative Analysis
•	Top 3 Best Performers
•	Habit-wise success rate across users
 Behavioral Pattern Analysis
•	Skip reason wise total skipped habits
•	Habit vs Skip Reason Matrix
•	Failure vs Success distribution
**🔵 Page 4 – Productivity Analysis Dashboard**
Idea Behind This Page
This page is designed to measure overall productivity performance and behavioral consistency of users.
Instead of only tracking completion counts, this dashboard focuses on:
•	Productivity efficiency
•	Mood consistency
•	Time utilization
•	Habit performance trends
It provides a performance monitoring view.
Problem This Page Solves
Many productivity systems only show:
•	Total tasks completed
•	Streak counts
But they fail to answer:
•	Is performance improving or declining?
•	Is mood stable while productivity increases?
•	Is time spent aligned with output?
•	Which habits are driving performance?
This page solves the problem of:
Measuring productivity in a structured and analytical way instead of just counting activities.
👤 Target Users
This page is designed for:
•	Individual users tracking personal productivity
•	Team leads monitoring employee engagement
•	Organizations analyzing performance trends
•	Coaches evaluating habit effectiveness
It provides a high-level performance overview.

 Key Insights from This Page
1.KPI Section
•	Completion Rate  Shows execution efficiency.
•	Average Mood  Measures emotional level.
•	Mood Stability   Indicates emotional consistency.
Lower value means more stable mood.
•	Total Active Days  Shows Total Time Used.
2. Monthly Completion Trend
Shows performance variation across months.
Helps identify:
•	Productivity peaks
•	Seasonal behavioral changes
This helps detect long-term consistency.

3.Category-wise Time Utilization
Shows where time is invested most.
Example: More time in Wellness than Finance.
This helps answer: Are users investing time in high-impact areas?

4.Top 3 Performing Habits
Identifies strongest habits contributing to productivity.
Helps in:
•	Recognizing effective routines

5.Mood Trend
Tracks emotional changes across months.
Helps correlate: Mood Trend Over a period.

Overall Insight of Page 1
This page answers:
•	How productive is the user?
•	Is performance stable?
•	Is emotional state aligned with output?
•	Which habits drive results?
**
🔴 Page 4 – Burnout Analysis Dashboard**
 Idea Behind This Page
This page is designed to detect early signs of burnout and disengagement.
Instead of focusing on what is completed, this page analyzes:
•	Skipping behavior
•	Partial completion
•	Mood volatility
•	Avoidance patterns
It acts as a behavioral risk monitoring system.
Problem This Page Solves
Traditional dashboards only celebrate success.
They do not detect:
•	Increasing skipping patterns
•	Drop in emotional stability
•	Repeated avoidance of certain habit categories
•	Early burnout signals
This page solves:
Identifying disengagement and burnout risk before productivity collapses.
👤 Target Users
This page is designed for:
•	HR teams monitoring employee well-being
•	Managers detecting performance risk
•	Individuals identifying self-burnout
•	Productivity coaches analyzing behavioral drop-offs
It focuses on risk detection instead of performance celebration.
 Key Insights from This Page
1.Skipping Rate 
Shows percentage of missed activities. Higher value indicates disengagement.
2.Partial Completion Rate 
Shows incomplete effort. This signals reduced motivation or low focus.
3.Mood Metrics
•	Average Mood: 
•	Mood Stability: (variation index)
High fluctuation combined with high skipping can signal burnout.

4. Skipping by Reason
Identifies root causes such as:
•	Work pressure
•	Health issues
•	Lack of motivation
•	Workload
•	Festivals or events
This helps move from symptom to cause analysis.

5.Top 3 Skipped Habits
Identifies most avoided activities.
Helps detect:
•	Habit fatigue
•	Low-priority habits
•	Overload in specific categories
6. Category-wise Skipping Rate
Shows which life areas are neglected most.
This supports behavioral pattern detection.
7.Performance Distribution (Donut Chart)
Breaks down:
•	Completed
•	Partial
•	Skipped
This shows behavioral composition rather than just totals.
Overall Insight of Page 2
This page answers:
•	Is the user at burnout risk?
•	Are skipping patterns increasing?
•	Which categories are being neglected?
•	What are the root causes of disengagement?
It acts as a Behavioral Risk Monitoring Dashboard.

**7. Real Life Usecase**

1.Corporate Performance & Employee Well-being
Organizations often struggle to measure:
•	Employee engagement
•	Productivity consistency
•	Early burnout signals
This system can be used by HR teams and managers to:
•	Monitor engagement levels
•	Identify declining performance trends
•	Detect increasing skipping patterns
•	Analyze workload-related stress indicators

2.Personal Productivity & Self-Monitoring
Individuals who track habits often only see:
•	Streak counts
•	Basic completion numbers
This project goes beyond that by analyzing:
•	Emotional stability
•	Time efficiency
•	Habit consistency
•	Behavioral drop-off patterns

3.Coaching & Mentorship Programs
Productivity coaches, therapists, or mentors can use this system to:
•	Monitor client consistency
•	Identify avoidance behavior
•	Correlate mood with performance
•	Recommend structured interventions
For example:
If fitness-related habits are consistently skipped due to workload, a coach can recommend workload adjustment or micro-habit restructuring.

4.Academic & Student Productivity Tracking
Educational institutions can apply this system to:
•	Track student study consistency
•	Detect stress-related performance drops
•	Identify disengagement patterns
This can support:
•	Academic counseling
•	Mental health monitoring
•	Performance improvement planning

