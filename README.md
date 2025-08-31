# Healthcare-Analytics-PowerBI

**Project Overview**

This project is a Healthcare Analytics Dashboard built in Power BI to monitor:
**Patient Demographics** (Age, Gender, Diagnosis distribution)
**Hospital Performance** (LOS, Readmission, Revenue)
**Treatment Adherence & Satisfaction Scores
KPIs aligned with industry benchmarks**

**Features & Visuals**
**KPI Cards** – Avg LOS, Readmission Rate, Treatment Adherence, Patient Satisfaction
**Demographics** – Age group distribution, Gender split (donut)
**Hospital Analysis** – Revenue by hospital, LOS comparison, Adherence trend
**Benchmarking** – Gauge chart with Target 90% Adherence
**Filters** – Hospital, Diagnosis, Region, Admission Date

**Data Modeling & DAX**
All important metrics are created as Measures for accuracy.
**Length of Stay** = DATEDIFF(Patient[Admission_Date], Patient[Discharge_Date], DAY)
**Avg LOS** = AVERAGE(Patient[Length_of_Stay])
**Readmission Rate (%)** =
DIVIDE(
    COUNTROWS(FILTER(Patient, Patient[Readmission_Flag] = 1)),
    COUNTROWS(Patient)
)
**Treatment Adherence (%)** = AVERAGE(Patient[Treatment_Adherence(%)])
**Patient Satisfaction** = AVERAGE(Patient[Satisfaction_Score])
**Age Groups (for Demographics)** = SWITCH(TRUE(),Patient[Age] >= 18 && Patient[Age] <= 30, "18-30",Patient[Age] >= 31 && Patient[Age] <= 45, "31-45",Patient[Age] >= 46 && Patient[Age] <= 60, "46-60",Patient[Age] >= 61, "61+","Unknown")
**Target Value (Gauge)** = 90

**Deliverables**

End-to-End Healthcare Analytics Dashboard using Power BI
Covers Patient Demographics, Treatment Adherence, Provider Performance, and Financials
Provides benchmarks & KPIs to support healthcare decision-making

