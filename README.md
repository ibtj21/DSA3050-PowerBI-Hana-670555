# Hotel Booking Demand Analysis in Power BI

## DSA 3050A – Business Intelligence & Data Visualization

**Student:** Hana Gashaw  
**Student ID:** 670555  
**Software:** Microsoft Power BI Desktop  
**Dataset:** Hotel Booking Demand  

![Hotel Booking Dataset](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/hotel.png)

---

## 1. Project Introduction

This project develops a Business Intelligence solution using Microsoft Power BI to analyze hotel booking demand, cancellation patterns, pricing, customer characteristics, and hotel performance. The project follows the complete BI workflow, from data acquisition and preparation to data modelling, DAX analysis, interactive dashboard development, and business interpretation.

The analysis uses the Hotel Booking Demand dataset, which contains **119,390 hotel booking records** from a resort hotel and a city hotel. The dataset provides information about booking characteristics, arrival dates, length of stay, guest composition, market segments, room types, booking channels, cancellation status, and average daily rates (ADR).

The main objective of the project is to transform the raw booking data into meaningful business intelligence that can help hotel management understand **booking demand, cancellation behaviour, pricing patterns, customer segments, and factors associated with booking cancellations**.

---

# SECTION A: DATASET SELECTION & UNDERSTANDING

## 1. The Source of the Dataset

The dataset used in this project is the **Hotel Booking Demand dataset**, originally documented by Antonio, de Almeida, and Nunes (2019) in the research publication *Hotel Booking Demand Datasets*, published in *Data in Brief* (DOI: 10.1016/j.dib.2018.11.126).

The original article released two separate hotel datasets:

- **H1 – Resort Hotel**
- **H2 – City Hotel**

For this project, a merged version of the two hotels—combined and lightly re-typed by Thomas Mock and Antoine Bichat for the **#TidyTuesday** project (`rfordatascience/tidytuesday`, 2020-02-11)—was used as the working file.

**Working dataset:**  
[Hotel Booking Demand Dataset – TidyTuesday](https://github.com/rfordatascience/tidytuesday/blob/main/data/2020/2020-02-11/hotels.csv)

The dataset contains **119,390 records and 32 variables**, covering hotel arrivals from **2015 to 2017**.

---

## 2. What the Dataset Represents

The dataset represents hotel booking information collected from hotel Property Management Systems. Each record contains information about a hotel booking, including cancellation status, booking lead time, arrival details, length of stay, guest characteristics, booking channels, room types, pricing, and reservation status.

The dataset covers bookings from two hotel types:

- **Resort Hotel**
- **City Hotel**

It provides information suitable for analysing hotel booking demand, cancellation behaviour, pricing patterns, customer characteristics, and differences between the two hotels.

The following screenshots show the raw Hotel Booking Demand dataset used as the starting point for the analysis.

![Raw Dataset 1](https://raw.githubusercontent.com/ibtj21/DSA3050-PowerBI-Hana-670555/main/screenshots/raw_data1.png)

![Raw Dataset 2](https://raw.githubusercontent.com/ibtj21/DSA3050-PowerBI-Hana-670555/main/screenshots/raw_data2.png)

![Raw Dataset 3](https://raw.githubusercontent.com/ibtj21/DSA3050-PowerBI-Hana-670555/main/screenshots/raw_data3.png)

---

## 3. Why the Dataset Was Selected

The Hotel Booking Demand dataset was selected because it satisfies the main dataset requirements for the DSA 3050A examination while remaining sufficiently understandable for meaningful Business Intelligence analysis.

The dataset provides:

- More than **20,000 records**
- Multiple numerical variables
- Multiple categorical variables
- Date-related information
- Variables suitable for KPI calculations
- Multiple dimensions for analysis, including hotel, country, market segment, customer type, room type, and booking channel
- Data-quality issues that can be investigated and addressed using Power Query

The dataset also provides a clear business problem around **hotel booking performance and cancellation behaviour**, creating opportunities to demonstrate data preparation, data modelling, DAX calculations, dashboard design, and business interpretation.

---

## 4. The Main Variables Available

| Variable | Description |
|---|---|
| `hotel` | Type of hotel: Resort Hotel or City Hotel |
| `is_canceled` | Indicates whether a booking was cancelled |
| `lead_time` | Number of days between booking and arrival |
| `arrival_date_year` | Year of arrival |
| `arrival_date_month` | Month of arrival |
| `arrival_date_week_number` | Week number of arrival |
| `arrival_date_day_of_month` | Day of arrival |
| `stays_in_weekend_nights` | Number of weekend nights |
| `stays_in_week_nights` | Number of weekday nights |
| `adults` | Number of adults |
| `children` | Number of children |
| `babies` | Number of babies |
| `country` | Country of the guest |
| `meal` | Meal type selected |
| `market_segment` | Market segment of the booking |
| `distribution_channel` | Distribution channel used for the booking |
| `is_repeated_guest` | Indicates whether the guest is a returning guest |
| `reserved_room_type` | Room type originally reserved |
| `assigned_room_type` | Room type assigned |
| `deposit_type` | Type of deposit |
| `customer_type` | Type of customer |
| `adr` | Average Daily Rate |
| `booking_changes` | Number of booking changes |
| `previous_cancellations` | Number of previous cancellations |
| `previous_bookings_not_canceled` | Number of previous bookings that were not cancelled |
| `days_in_waiting_list` | Number of days spent on the waiting list |
| `required_car_parking_spaces` | Number of required parking spaces |
| `total_of_special_requests` | Number of special requests |
| `reservation_status` | Final reservation status |
| `reservation_status_date` | Date of the final reservation status |

---

## 5. The Business / Analytical Problem to Be Investigated

The main business problem investigated in this project is:

> **How can hotel management better understand booking demand and cancellation behaviour in order to identify important patterns, customer segments, pricing trends, and areas requiring management attention?**

The analysis will particularly investigate differences between the **City Hotel and Resort Hotel** and examine factors associated with booking cancellations, including lead time, market segment, distribution channel, customer type, deposit type, and pricing.

---

## 6. Analytical Questions

The Power BI solution will aim to answer the following questions:

1. **How does hotel booking demand change over time?**

2. **What is the overall cancellation rate, and how does it differ between the City Hotel and Resort Hotel?**

3. **Which market segments, customer types, and distribution channels contribute the most bookings?**

4. **How does the Average Daily Rate (ADR) vary across hotels, room types, seasons, and market segments?**

5. **Which factors are associated with higher booking cancellation rates?**

6. **How does booking lead time relate to cancellation behaviour?**

7. **How do booking patterns differ between the City Hotel and Resort Hotel?**

8. **Which countries contribute the highest number of bookings?**

9. **How does booking behaviour differ between repeated and non-repeated guests?**

10. **Which areas of hotel booking performance require management attention?**
