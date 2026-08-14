# Hotel Booking Demand Analysis in Power BI

## DSA 3050A – Business Intelligence & Data Visualization

**Student:** Hana Gashaw  
**Student ID:** 670555  
**Software:** Microsoft Power BI Desktop  
**Dataset:** Hotel Booking Demand  

---

## 1. Project Introduction

This project develops a Business Intelligence solution using Microsoft Power BI to analyze hotel booking demand, cancellation patterns, pricing, customer characteristics, and hotel performance. The project follows the complete BI workflow, from data acquisition and preparation to data modelling, DAX analysis, interactive dashboard development, and business interpretation.

The analysis uses the Hotel Booking Demand dataset, which contains **119,390 hotel booking records** from a resort hotel and a city hotel. The dataset provides information about booking characteristics, arrival dates, length of stay, guest composition, market segments, room types, booking channels, cancellation status, and average daily rates (ADR).

The main objective of the project is to transform the raw booking data into meaningful business intelligence that can help hotel management understand **booking demand, cancellation behaviour, pricing patterns, customer segments, and factors associated with booking cancellations**.

---

## 2. Dataset Source

The dataset used in this project is the **Hotel Booking Demand dataset** originally documented by Antonio, Almeida, and Nunes in the research publication *Hotel Booking Demand Datasets*.

The dataset contains booking records from two hotels:

- Resort Hotel
- City Hotel

The dataset covers hotel arrivals from **2015 to 2017** and contains **119,390 records and 32 variables**.

**Original dataset source:**  
[Hotel Booking Demand Datasets – ISCTE-IUL](https://repositorio.iscte-iul.pt/handle/10071/16929)

The original publication provides the documentation and description of the dataset and its variables.

---

## 3. What the Dataset Represents

The dataset represents hotel booking information collected from hotel Property Management Systems. Each record contains information about a hotel booking, including whether the booking was cancelled, how far in advance it was made, the length of stay, guest characteristics, booking channels, room types, pricing, and reservation status.

The dataset therefore provides an opportunity to investigate both **booking demand and cancellation behaviour**, as well as differences between the two hotels and different customer and market segments.

---

## 4. Why This Dataset Was Selected

The Hotel Booking Demand dataset was selected because it satisfies the main dataset requirements for the examination while remaining sufficiently understandable for meaningful Business Intelligence analysis.

It contains:

- More than **20,000 records**
- Multiple numerical variables
- Multiple categorical variables
- Date-related information
- Variables suitable for KPI calculations
- Information supporting different dimensions of analysis
- Data-quality issues that can be investigated and addressed using Power Query

The dataset also provides a strong business problem around **hotel booking performance and cancellations**, allowing the project to demonstrate data preparation, modelling, DAX calculations, dashboard design, and business interpretation.

---

## 5. Main Variables

Some of the main variables used in the analysis include:

| Variable | Description |
|---|---|
| `hotel` | Type of hotel: Resort Hotel or City Hotel |
| `is_canceled` | Indicates whether a booking was cancelled |
| `lead_time` | Number of days between booking and arrival |
| `arrival_date_year` | Year of arrival |
| `arrival_date_month` | Month of arrival |
| `arrival_date_day_of_month` | Day of arrival |
| `stays_in_weekend_nights` | Number of weekend nights |
| `stays_in_week_nights` | Number of weekday nights |
| `adults` | Number of adults |
| `children` | Number of children |
| `babies` | Number of babies |
| `country` | Country of the guest |
| `market_segment` | Market segment of the booking |
| `distribution_channel` | Booking distribution channel |
| `reserved_room_type` | Room type originally reserved |
| `assigned_room_type` | Room type assigned |
| `deposit_type` | Type of deposit |
| `customer_type` | Type of customer |
| `adr` | Average Daily Rate |
| `total_of_special_requests` | Number of special requests |
| `reservation_status` | Final reservation status |

Additional calculated fields will be created during the data preparation and modelling stages where appropriate.

---

## 6. Business / Analytical Problem

The main business problem investigated in this project is:

> **How can hotel management better understand booking demand and cancellation behaviour in order to identify important patterns, customer segments, pricing trends, and areas requiring management attention?**

The analysis will particularly investigate differences between the two hotels and examine factors that are associated with booking cancellations.

---

## 7. Analytical Questions

The Power BI solution will aim to answer the following questions:

1. **How does hotel booking demand change over time?**

2. **What is the cancellation rate, and how does it differ between the City Hotel and Resort Hotel?**

3. **Which market segments, customer types, and distribution channels contribute the most bookings?**

4. **How does the Average Daily Rate (ADR) vary across hotels, room types, seasons, and market segments?**

5. **Which factors are associated with higher booking cancellation rates?**

6. **How do lead time and booking characteristics relate to cancellations?**

7. **How do booking patterns differ between the City Hotel and Resort Hotel?**

8. **Which countries contribute the highest number of bookings?**

9. **How do repeat guests differ from non-repeat guests in their booking behaviour?**

10. **What business areas require management attention based on the observed booking and cancellation patterns?**

---

## 8. BI Development Approach

The project will follow a complete Business Intelligence workflow:

**Raw Dataset → Data Profiling → Power Query → Data Model → DAX Measures → Interactive Dashboards → Business Insights**

The solution will demonstrate:

- Data acquisition and understanding
- Data cleaning and transformation using Power Query
- Data modelling and relationships
- DAX calculations and analytical measures
- Interactive dashboard development
- Data visualization and storytelling
- Business interpretation and recommendations
