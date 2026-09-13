
# HealthConnect Clinic — Data Analytics

## Improving Patient Appointment Attendance and Healthcare Support Using Data and AI

**AnalystLab Africa Experience Lab — Data Analytics Track**

## Project Overview

This project investigates how HealthConnect Clinic can use data and AI to reduce missed appointments and improve the patient support experience.

The Week 6 Data Analytics work builds on the validated Week 5 analysis by moving from descriptive KPI reporting toward advanced segmentation, relationship analysis, KPI validation, decision support, dashboard refinement, and cross-track integration with Data Science.

The analysis uses a fictional healthcare appointment dataset containing **5,000 appointment records, 18 variables, and 1,696 unique patients**.

### Central Project Question

> **How can HealthConnect Clinic use data and AI to reduce missed appointments and improve the patient support experience?**

---

# Week 6 — Advanced Analysis, KPI Validation & Decision Support

### Objective

The objective of Week 6 was to investigate important Week 5 findings more deeply, validate the most important KPIs, identify high-risk appointment segments, refine the Power BI dashboard, and provide evidence-based analytical inputs for subsequent Data Science work.

Week 6 deliberately extends rather than repeats the Week 5 analysis.

### Key Activities

- Advanced analysis of booking lead time and no-show behaviour
- Analysis of previous no-show history as a behavioural risk indicator
- Investigation of reminder status across relevant segments
- Combined analysis of booking lead time and previous no-show history
- High-risk segment identification
- Secondary segmentation by distance and appointment type
- KPI validation and refinement
- Power BI dashboard enhancement
- Evidence-based decision-support development
- Data Analytics → Data Science integration
- Documentation of limitations, risks, and Week 7 testing requirements

---

# Key Validated Findings

### Core Appointment Outcomes

| Metric | Result |
|---|---:|
| Total Appointments | **5,000** |
| Eligible Appointments | **4,737** |
| Attended Appointments | **2,314** |
| No-Show Appointments | **2,423** |
| Cancelled Appointments | **263** |
| No-Show Rate | **51.15%** |
| Attendance Rate | **48.85%** |
| Cancellation Rate | **5.26%** |

### Behavioural Risk

Appointments involving patients with at least one previous no-show recorded a:

**57.83% No-Show Rate**

compared with:

**46.30%** among patients with no previous no-shows.

This represents an **11.53 percentage-point difference**.

### Booking Lead Time

No-show rates increased across longer booking lead-time groups:

| Booking Lead Time | No-Show Rate |
|---|---:|
| 0 days | 25.93% |
| 1–3 days | 26.85% |
| 4–7 days | 32.25% |
| 8–14 days | 35.19% |
| 15–30 days | 45.53% |
| 31–60 days | 63.95% |

### Highest Identified High-Risk Segment

The strongest combined risk pattern identified in Week 6 was:

**31–60 days booking lead time + 1 or more previous no-shows**

This segment recorded a:

### **70.52% No-Show Rate**

This finding became the primary Week 6 decision-support indicator.

### Reminder Analysis

Overall:

- Reminder sent: **49.86%**
- No reminder: **54.63%**
- Difference: **4.77 percentage points**

Within the high-risk segment:

- Reminder sent: **69.21%**, n = 708
- No reminder: **73.98%**, n = 269

These findings represent **observed associations and should not be interpreted as evidence of causality**.

---

# KPI Framework

The Week 6 analysis refined the KPI framework into the following categories:

### Core KPIs

- No-Show Rate — **51.15%**
- Attendance Rate — **48.85%**

### Behavioural KPI

- Repeat No-Show Rate — **57.83%**

### Association Metric

- No-Show Rate by Reminder Status
  - Reminder Sent — **49.86%**
  - No Reminder — **54.63%**

### Decision-Support Indicator

- High-Risk Segment No-Show Rate — **70.52%**

### Context Metric

- Cancellation Rate — **5.26%**

---

# Power BI Dashboard

Week 6 expanded the Power BI dashboard from general attendance monitoring to targeted appointment-risk analysis.

## Dashboard Page 1

**HealthConnect — Advanced Appointment Risk Analysis**

Includes:

- Total Appointments
- Eligible Appointments
- No-Show Rate
- Attendance Rate
- Cancellation Rate
- No-Show Rate by Booking Lead Time
- No-Show Rate by Previous No-Show History
- Booking Lead Time × Previous No-Show History
- No-Show Rate by Reminder Status Within High-Risk Segment
- Appointment Type slicer
- Appointment Day slicer
- Reminder Status slicer

## Dashboard Page 2

**HealthConnect — High-Risk Segment Deep Dive**

Includes:

- High-Risk Segment No-Show Rate — **70.52%**
- No-Show Rate by Distance Within High-Risk Segment
- No-Show Rate by Appointment Type Within High-Risk Segment

The dashboard is designed to support evidence-based prioritisation rather than simply reporting overall attendance performance.

---

# Data Analytics → Data Science Integration

Week 6 established a formal analytical contribution to the Data Science track.

The Data Analytics analysis identified candidate variables and relationships that may support subsequent predictive modelling, including:

- `previous_no_shows`
- Previous No-Show Status
- `booking_lead_days`
- Booking Lead Group
- `distance_to_clinic_km`
- Distance Group
- `appointment_type`
- `reminder_sent`
- Booking Lead Time × Previous No-Show History
- High-Risk Segment × Reminder Status

The analysis also identified potential data-leakage and timing considerations.

In particular:

- `appointment_outcome` must remain the target variable rather than a predictive input.
- `reminder_sent` requires confirmation of its timing relative to the intended prediction point.
- `waiting_time_minutes` was not automatically treated as a pre-appointment predictor because its timing relative to attendance was not established.

The Week 6 work therefore provides **analytical inputs and feature candidates for Data Science rather than claiming a completed predictive model**.

---

# Data Quality and Validation

The Week 6 analysis retained the validated data-quality foundation established during earlier project stages.

Key checks included:

- 5,000 appointment records
- 5,000 unique appointment IDs
- No full-row duplicates identified
- 4,737 eligible appointments
- 2,314 attended appointments
- 2,423 no-show appointments
- 263 cancelled appointments
- No booking-date/appointment-date logical violations
- No booking lead-time calculation mismatches
- No previous-no-show/history logical violations
- Missing-value patterns reviewed and documented

The missing `reminder_channel` values were identified as structural because they correspond to records where no reminder was sent.

---

# Limitations

The analysis is based on observational appointment data. Therefore, the findings identify associations and patterns rather than causal effects.

Important limitations include:

- Reminder timing was not established.
- Waiting-time timing relative to appointment attendance was uncertain.
- Some segments have relatively small sample sizes.
- Highly segmented analysis can produce unstable estimates.
- Distance and appointment-type patterns should be treated as secondary indicators.
- Predictive modelling requires additional feature-timing and leakage validation.

These limitations are incorporated into the Week 7 testing requirements.

---

# Week 7 Testing Priorities

The Week 6 findings provide the analytical foundation for the next stage of the project.

Priority testing areas include:

1. Reconciliation of all core KPIs.
2. Stability of the 70.52% high-risk segment.
3. Validation of booking lead-time patterns.
4. Validation of previous no-show history.
5. Testing of the Booking Lead Time × Previous No-Show History interaction.
6. Further testing of reminder associations.
7. Review of small-sample segments.
8. Validation of reminder timing for predictive use.
9. Confirmation of the modelling suitability of waiting time.
10. End-to-end validation between the analytical findings, dashboard, and Data Science development.

---

# Tools & Technologies

- **Microsoft Power BI**
- **DAX**
- **Microsoft Excel**
- **GitHub**

---

# Repository Contents

The repository contains project materials developed across the HealthConnect Clinic Data Analytics track, including:

- Week 4 problem understanding and analytical planning
- Week 5 data preparation, KPI development, EDA, and initial dashboard development
- Week 6 advanced analysis and validation
- Power BI dashboard development
- Analytical reports
- Supporting data-quality and validation documentation
- Advanced analysis tables
- KPI validation evidence
- Cross-track integration documentation

---

# Project Progression

| Week | Focus | Status |
|---|---|---|
| Week 4 | Problem Understanding, Resource Review & Solution Planning | Complete |
| Week 5 | Analysis, Development & Initial Implementation | Complete |
| Week 6 | Integration, Advanced Development & Validation | **Complete** |
| Week 7 | Testing, Refinement & End-to-End Validation | Next Stage |
| Week 8 | Final Integration & Presentation | Upcoming |

---

# Overall Analytical Contribution

Week 6 moved the HealthConnect Clinic project from broad attendance monitoring toward **targeted, evidence-based appointment-risk analysis**.

The analysis identified booking lead time and previous no-show history as the strongest observed risk dimensions in the available data. Their combination identified a high-risk segment with a **70.52% no-show rate**.

The resulting findings strengthened KPI reporting, improved the Power BI dashboard, provided decision-support insights, and supplied candidate analytical inputs for Data Science while maintaining appropriate caution around causality, data leakage, and feature timing.

---

## Author

**Suh Cheo Cyprain**

Data Analytics Track  
AnalystLab Africa Experience Lab