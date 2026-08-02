Power BI Project – Panic Attack Data Analysis (Snowflake)
Problem Statement
Developed an interactive Power BI dashboard to analyze panic attack patient data and identify trends across demographics, symptoms, medical history, trigger factors, and panic severity. The objective was to help healthcare professionals and NGOs understand patient patterns and support data-driven awareness and intervention strategies.
Tech Stack
Power BI Desktop
Snowflake
SQL
Power Query
DAX
Dataset
Clinical panic attack dataset stored in Snowflake, containing patient demographics, symptoms (dizziness, sweating, trembling, shortness of breath), panic scores, trigger reasons, medical history, sleep duration, heart rate, and panic attack frequency. Data was imported into Power BI through the Snowflake connector and transformed using Power Query.
Key Responsibilities
Connected Power BI to Snowflake and imported healthcare data.
Performed data cleaning and transformation using Power Query (handled null values, corrected data types, replaced invalid values, and created derived columns).
Wrote SQL queries in Snowflake to validate and understand source data.
Designed an interactive multi-page Power BI dashboard with KPI cards, bar charts, slicers, and demographic analysis.
Implemented DAX calculated columns and measures for business metrics and percentage calculations.
Enabled interactive filtering using Gender, Panic Score, Trigger Reason, Medical History, and Age Group.
Important DAX Used
IF() and SWITCH() – Created Age Group and Panic Score classifications.
COUNTROWS() – Counted patients meeting specific conditions.
FILTER() – Applied conditional filtering for symptom analysis.
DIVIDE() – Calculated symptom percentages while avoiding divide-by-zero errors.
CALCULATE() – Modified filter context for KPI calculations.
Sample DAX Measures
Age Group =
SWITCH(
    TRUE(),
    PANIC_ATTACK_DATA[AGE] <= 12, "Minor",
    PANIC_ATTACK_DATA[AGE] <= 24, "Young Adult",
    PANIC_ATTACK_DATA[AGE] <= 64, "Adult",
    "Senior"
)
% Patients with Dizziness =
DIVIDE(
    CALCULATE(
        COUNTROWS(PANIC_ATTACK_DATA),
        PANIC_ATTACK_DATA[DIZZINESS] = TRUE()
    ),
    COUNTROWS(PANIC_ATTACK_DATA)
)
Dashboard Highlights
Executive overview with patient KPIs.
Symptom distribution analysis.
Age Group vs Panic Score analysis.
Trigger Reason and Medical History analysis.
Interactive slicers for demographic and clinical segmentation.
Percentage-based KPIs for symptom prevalence.
Resume ready

Panic Attack Data Analysis Dashboard | Power BI, Snowflake, SQL, DAX
Developed an end-to-end Power BI dashboard by integrating patient data from Snowflake to analyze panic attack trends across demographics, symptoms, and clinical history.
Performed data cleaning and transformation using Power Query and validated source data with SQL before building the semantic model.
Created DAX measures and calculated columns using CALCULATE, COUNTROWS, FILTER, DIVIDE, IF, and SWITCH to derive KPIs, age-group segmentation, and symptom prevalence metrics.
Designed interactive dashboards with KPI cards, bar charts, slicers, and drill-down analysis for panic scores, trigger reasons, medical history, and age groups.
# Panic_attack_Power_Bi_Snowflake_Project
BI Projects
https://github.com/deb0707/Panic_attack_Power_Bi_Snowflake_Project/blob/main/Panic_Attack_Power-Bi_Snowflake%20Project.jpg
