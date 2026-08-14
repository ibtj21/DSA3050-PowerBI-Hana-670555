# Hotel Booking Demand Analysis in Power BI

## DSA 3050A – Business Intelligence & Data Visualization

**Student:** Hana Gashaw  
**Student ID:** 670555  
**Software:** Microsoft Power BI Desktop  
**Dataset:** Hotel Booking Demand  

![Hotel Booking Dataset](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/01_raw_data/hotel.png)

---

# Project Introduction

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

![Raw Dataset 1](https://raw.githubusercontent.com/ibtj21/DSA3050-PowerBI-Hana-670555/main/screenshots/01_raw_data/raw_data1.png)

![Raw Dataset 2](https://raw.githubusercontent.com/ibtj21/DSA3050-PowerBI-Hana-670555/main/screenshots/01_raw_data/raw_data2.png)


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

The analysis focuses on understanding how hotel booking demand changes over time and how booking outcomes differ across the **City Hotel and Resort Hotel**. It examines booking volume, cancellation rates, market segments, customer types, distribution channels, pricing, room types, geographic patterns, and differences between repeated and non-repeated guests.

A particular focus of the analysis is to identify factors associated with **booking cancellations**, including booking lead time and other characteristics of the reservation. The project will also examine **Average Daily Rate (ADR)** across different hotel, room, seasonal, and market segments to identify pricing patterns.

The analysis is intended to provide hotel management with a clearer view of:

- **Booking demand and trends over time**
- **Differences in performance between the two hotels**
- **Cancellation patterns and their associated factors**
- **The contribution of different market and customer segments**
- **Pricing patterns based on ADR**
- **Geographic distribution of bookings**
- **Differences between repeated and non-repeated guests**

The overall objective is to transform the raw hotel booking data into **actionable business intelligence** that can help management identify important patterns, understand cancellation behaviour, and determine areas that may require further investigation or management attention.

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


---

## *Transition to Data Preparation*

Having established the dataset, its characteristics, and the key analytical questions, the next stage is to begin the **Business Intelligence development process**. The raw dataset is first loaded into **Microsoft Power BI Desktop**, where its structure and data quality can be examined before applying any cleaning and transformation steps using Power Query.

The following screenshot shows the initial loading of the raw dataset into Power BI.

![Loading Raw Dataset into Power BI](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/01_raw_data/load_data.png)

> **Figure 1: Initial loading of the Hotel Booking Demand dataset into Power BI Desktop.**

The subsequent stage focuses on profiling the imported data, identifying data-quality issues, and applying appropriate transformations in Power Query.

# SECTION B: POWER QUERY – DATA CLEANING & TRANSFORMATION

Power Query was used to prepare the raw Hotel Booking Demand dataset for analysis before developing the data model and DAX measures. The transformations were based on data-quality issues and analytical requirements identified during the initial inspection of the dataset.

The following transformations were applied to improve data quality, consistency, usability, and analytical readiness.

---

## 1. Handling Errors — `children` Column

**Problem:**
The `children` column was already assigned the appropriate **Whole Number** data type, but four records contained the value `NA`. These non-numeric values resulted in `DataFormat.Error` when Power Query attempted to interpret the column as numeric.

![Filtered Invalid Rows](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/02_power_query/Handling_errors/filtered_invalid_rows.png)

**Transformation:**
Used **Replace Errors** on the `children` column and replaced the four error values with `null`.

![Replace Errors](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/02_power_query/Handling_errors/replace_errors.png)

**Reason:**
The `children` field represents a numerical count and should not contain text values. Replacing the errors with `null` preserves the affected records without incorrectly assuming that the missing value represents zero children.

**Result:**
The `children` column remained a valid **Whole Number** field and could be used in numerical calculations without conversion errors.

---

## 2. Removing Duplicates

**Problem:**
The raw dataset contained **31,994 exact duplicate rows**, meaning that identical records appeared more than once across the dataset.

**Transformation:**
Used **Remove Duplicates** in Power Query to identify and remove exact duplicate records.

![Removing Duplicates](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/02_power_query/remove_duplicates/remove_duplicates.png)

**Reason:**
Duplicate records could artificially increase booking counts and distort analytical results, including cancellation rates, guest counts, and other KPI calculations.

**Result:**
The exact duplicate records were removed, leaving a cleaner dataset for subsequent analysis and modelling.

![Rows After Duplicate Removal](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/02_power_query/remove_duplicates/after_removal.png)

**Figure:** Dataset after removing exact duplicate records, leaving **87,396 rows**.

---

## 3. Handling Missing/Null Values

**Problem:**
Missing values were identified in several categorical fields, including `country`, `agent`, and `company`.

**Transformation:**
Missing values were handled using meaningful replacement categories:

* `country` → `Unknown`

![Handling Missing Country Values](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/02_power_query/Handling_missing_values/fill_country.png)

* `agent` → `Not Recorded`

![Handling Missing Agent Values](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/02_power_query/Handling_missing_values/fill_agent.png)

* `company` → `Not Applicable`

![Handling Missing Company Values](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/02_power_query/Handling_missing_values/fill_company.png)

**Reason:**
The affected booking records were not removed because the missing information in these fields did not make the entire booking unusable. Meaningful categories allow the records to remain available for analysis while distinguishing missing or non-applicable information from valid categories.

**Result:**
Missing categorical values were handled consistently, reducing unexplained blanks in subsequent analysis and visualizations while preserving the booking records.

---

## 4. Replacing Incorrect Values — `adr`

**Problem:**
The `adr` (Average Daily Rate) field contained one negative value of **-6.38**. A negative daily hotel rate is not meaningful for the intended pricing analysis.

![Negative ADR Value](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/02_power_query/Replacing%20Incorrect%20Values/negative_adr.png)

**Transformation:**
The negative ADR record was identified using a numeric filter and removed from the analytical dataset.

**Reason:**
Retaining the invalid value could distort pricing-related calculations such as average ADR and other measures derived from the daily rate.

**Result:**
The invalid negative ADR record was removed, leaving valid ADR values for pricing and performance analysis.

---

## 5. Merging Columns — Creating `Arrival Date`

**Problem:**
Arrival information was distributed across three separate fields: `arrival_date_year`, `arrival_date_month`, and `arrival_date_day_of_month`. Using these fields separately would make date-based analysis less convenient.

**Transformation:**
Merged the arrival year, month, and day information to create a unified **Arrival Date** field.

![Merging Arrival Date Columns](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/02_power_query/Merge_columns/merge_columns.png)

**Reason:**
A single date field provides a more convenient basis for time-based filtering, trend analysis, and the development of the dedicated Date dimension in the data model.

**Result:**
The dataset contains a unified arrival date that can be used for chronological analysis and date-based relationships.

---

## 6. Creating Custom Columns — `Total Stay Nights`

**Problem:**
The duration of each booking was divided between `stays_in_weekend_nights` and `stays_in_week_nights`. Analysing the complete duration would therefore require combining the two fields repeatedly.

**Transformation:**
Created a custom column named **`Total Stay Nights`** using:

`stays_in_weekend_nights + stays_in_week_nights`

![Creating Custom Column - Total Stay Nights](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/02_power_query/Creating_custom_columns/custom_column.png)

**Reason:**
A single measure of total stay duration is more convenient for analysing booking behaviour, length of stay, and hotel demand.

**Result:**
Each booking now has a `Total Stay Nights` value representing the complete duration of the stay.

---

## 7. Creating Conditional Columns — `Cancellation Status`

**Problem:**
The `is_canceled` field represents cancellation using numeric values (`0` and `1`), which are less intuitive for business users when interpreting reports and dashboard visuals.

**Transformation:**
Created a conditional column named **`Cancellation Status`**:

* `1` → `Cancelled`
* `0` → `Not Cancelled`

![Creating Conditional Column](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/02_power_query/Creating_conditional_columns/conditional_column.png)

**Reason:**
Descriptive categories are easier to interpret in filters, tables, charts, and KPI analysis than numeric binary codes.

**Result:**
The dataset now contains a business-friendly `Cancellation Status` field that can be used directly in Power BI analysis and visualizations.

---

## 8. Extracting Information from Dates — `Month`

**Problem:**
The `reservation_status_date` field contains a complete date, but month-level analysis requires an appropriate time component.

**Transformation:**
Extracted the **month** from `reservation_status_date` to create a new `Month` field.

![Extracting Reservation Month](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/02_power_query/Extracting_information_from_dates/extract_month.png)

**Reason:**
Monthly information supports analysis of reservation-status patterns and allows booking outcomes to be examined across different periods.

**Result:**
A month-level field was created from `reservation_status_date` for use in time-based analysis.

---

## 9. Renaming Fields Appropriately — `Reservation Month`

**Problem:**
The extracted month field was initially named simply `Month`, which did not clearly indicate which date field the month originated from and could create ambiguity when additional date attributes are introduced.

**Transformation:**
Renamed the field from **`Month`** to **`reservation_month`**.

![Renaming Field](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/02_power_query/Renaming_fields_appropriately/renaming.png)

**Reason:**
Clear and descriptive field names improve data-model readability and reduce ambiguity when working with multiple date-related attributes.

**Result:**
The field is now explicitly identified as `reservation_month`, making its purpose clearer for subsequent modelling, DAX calculations, and dashboard development.

![Renamed Field Result](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/02_power_query/Renaming_fields_appropriately/result.png)

---

## Power Query Transformation Summary

The Power Query preparation stage demonstrated the following transformation categories:

|  # | Transformation                    | Main Purpose                                   |
| -: | --------------------------------- | ---------------------------------------------- |
|  1 | Handling Errors                   | Resolved invalid `NA` values in `children`     |
|  2 | Removing Duplicates               | Removed exact duplicate records                |
|  3 | Handling Missing/Null Values      | Addressed missing categorical information      |
|  4 | Replacing Incorrect Values        | Removed the invalid negative ADR value         |
|  5 | Merging Columns                   | Created a unified `Arrival Date`               |
|  6 | Creating Custom Columns           | Created `Total Stay Nights`                    |
|  7 | Creating Conditional Columns      | Created `Cancellation Status`                  |
|  8 | Extracting Information from Dates | Extracted month from `reservation_status_date` |
|  9 | Renaming Fields Appropriately     | Renamed `Month` to `reservation_month`         |

## *Transition to Data Modelling*

The Power Query stage transformed the raw Hotel Booking Demand dataset into a cleaner and analysis-ready structure by addressing data-quality issues and creating useful analytical fields. With the data prepared, the next stage is **data modelling**, where the cleaned data will be organized into an appropriate analytical structure, relationships will be established between tables, and a dedicated Date dimension will be created to support efficient analysis.

This stage will provide the foundation for developing **DAX measures, interactive dashboards, and meaningful business insights**.

