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

For this project, a merged version of the two hotels—combined and lightly re-typed by Thomas Mock and Antoine Bichat for the **#TidyTuesday** project (`rfordatascience/tidytuesday`, 2020-02-11)—was used as the working file.Both hotels in this dataset are located in Portugal.

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


### Power Query Applied Steps

The following screenshot summarizes the sequence of transformations applied during the Power Query data-cleaning and preparation stage. The Applied Steps pane provides evidence that the raw dataset was systematically transformed before being used in the analytical model.

![Power Query Applied Steps](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/02_power_query/Applied_steps.png)

## *Transition to Data Modelling*

The Power Query stage transformed the raw Hotel Booking Demand dataset into a cleaner and analysis-ready structure by addressing data-quality issues and creating useful analytical fields. With the data prepared, the next stage is **data modelling**, where the cleaned data will be organized into an appropriate analytical structure, relationships will be established between tables, and a dedicated Date dimension will be created to support efficient analysis.

This stage will provide the foundation for developing **DAX measures, interactive dashboards, and meaningful business insights**.


# SECTION C: DATA MODELLING

## 1. Identification of the Main Fact Table

The main fact table in the analytical model is **`FactBooking`**. It represents the central booking-level transactional data, where each row corresponds to an individual hotel booking record.

`FactBooking` contains the numerical measures and booking-level attributes required for analysis, including cancellation status, lead time, stay duration, guest counts, Average Daily Rate (ADR), booking changes, previous booking behaviour, special requests, and reservation status.

The fact table also contains foreign keys linking each booking to the relevant dimension tables:

* `HotelKey`
* `CountryKey`
* `RoomKey`
* `MarketSegmentKey`
* `ArrivalDateKey`

The original `hotels` query was retained as a **staging/source query** in Power Query but was not used as a final analytical table. This prevents the final model from containing both the original flat table and the analytical fact table.

#### *Why FactBooking Was Selected*

FactBooking was selected as the central fact table because each record represents an individual hotel booking and contains the measurable values and booking-level information required for the analysis. It includes measures such as ADR, lead time, stay duration, guest counts, cancellations, and special requests, making it the main table from which business performance indicators can be calculated.

---

## 2. Creation of Dimension Tables

A **Star Schema** was developed around `FactBooking`. Five dimensions were created based on the analytical requirements of the project:

### DimHotel

`DimHotel` contains the unique hotel categories:

* City Hotel
* Resort Hotel

**Key:** `HotelKey`

#### *Why DimHotel Was Created*

DimHotel was created to separate hotel-level descriptive information from the booking transactions. It allows bookings to be filtered and compared between City Hotel and Resort Hotel and supports analysis of differences in demand, cancellations, pricing, and other performance indicators.

---

### DimCountry

`DimCountry` contains the unique country values associated with bookings.

**Key:** `CountryKey`

#### *Why DimCountry Was Created*

DimCountry was created to support geographic analysis of booking behaviour. Separating country information into a dimension allows the report to analyse booking volume and cancellation patterns by country while keeping the fact table focused on booking-level information.

---

### DimRoom

`DimRoom` contains unique **reserved room types**.

**Key:** `RoomKey`

#### *Why DimRoom Was Created*

DimRoom was created from the reserved room types to provide a dedicated analytical view of room demand. It allows the report to examine how bookings are distributed across reserved room types while keeping the actual assigned room type in FactBooking for comparison and further analysis.

The `assigned_room_type` field remains in `FactBooking` because it represents the room actually assigned to the guest. Keeping the two fields separate also allows later analysis of differences between reserved and assigned room types.

---

### DimMarketSegment

`DimMarketSegment` contains the unique market segments represented in the booking data.

**Key:** `MarketSegmentKey`

#### *Why DimMarketSegment Was Created*

DimMarketSegment was created to provide a structured way of analysing bookings according to their market segment. It supports comparisons of booking volume, cancellation behaviour, and pricing across different segments without unnecessarily creating separate dimensions for every low-cardinality categorical field.

Fields such as `meal`, `deposit_type`, `distribution_channel`, and `customer_type` were retained as booking-level attributes rather than creating unnecessary additional dimensions. This keeps the model relatively simple while preserving the information required by the analytical questions.

---

### DimDate

A dedicated **`DimDate`** table was created because the dataset contains extensive date information and the project requires time-based analysis.

**Key:** `DateKey`

The Date dimension contains attributes such as:

* `Date`
* `DateKey`
* `Year`
* `Quarter`
* `Month Number`
* `Month Name`
* `Week Number`
* `Day`
* `Day of Week`
* `Day of Week Number`

#### *Why DimDate Was Created*

DimDate was created because the project requires extensive time-based analysis. It provides a consistent set of year, quarter, month, week, and day attributes that can be used to analyse booking trends and support DAX time-intelligence calculations.

---

## 3. Primary and Foreign Keys

Numeric keys were created for the dimension tables to provide unique identifiers for relationships.

| Table              | Primary Key        |
| ------------------ | ------------------ |
| `DimHotel`         | `HotelKey`         |
| `DimCountry`       | `CountryKey`       |
| `DimRoom`          | `RoomKey`          |
| `DimMarketSegment` | `MarketSegmentKey` |
| `DimDate`          | `DateKey`          |

The corresponding foreign keys were added to `FactBooking`:

| FactBooking Foreign Key | Related Dimension                    |
| ----------------------- | ------------------------------------ |
| `HotelKey`              | `DimHotel[HotelKey]`                 |
| `CountryKey`            | `DimCountry[CountryKey]`             |
| `RoomKey`               | `DimRoom[RoomKey]`                   |
| `MarketSegmentKey`      | `DimMarketSegment[MarketSegmentKey]` |
| `ArrivalDateKey`        | `DimDate[DateKey]`                   |

Using numeric keys provides a clear and consistent basis for establishing the relationships between the fact table and dimension tables.

---

## 4. Table Relationships

The model follows a Star Schema structure in which the dimension tables provide descriptive information and the fact table contains the booking records and measures.

The intended relationships are:

```text
DimHotel[HotelKey]
        1
        |
        *
FactBooking[HotelKey]


DimCountry[CountryKey]
        1
        |
        *
FactBooking[CountryKey]


DimRoom[RoomKey]
        1
        |
        *
FactBooking[RoomKey]


DimMarketSegment[MarketSegmentKey]
        1
        |
        *
FactBooking[MarketSegmentKey]


DimDate[DateKey]
        1
        |
        *
FactBooking[ArrivalDateKey]
```

Each dimension contains unique key values, while the corresponding key can occur multiple times in `FactBooking` because many bookings can belong to the same hotel, country, room type, market segment, or date.

---

## 5. Relationship Cardinality

All dimension-to-fact relationships use **one-to-many (1:*) cardinality**.

For example:

> One hotel can be associated with many booking records, while each booking belongs to one hotel.

Therefore:

`DimHotel (1) → FactBooking (*)`

The same principle applies to the country, room, market segment, and date dimensions.

The one-to-many structure avoids unnecessary many-to-many relationships and provides a clear analytical path between descriptive dimensions and booking records.

---

## 6. Cross-Filter Direction

The relationships are designed with **Single** cross-filter direction, with filters flowing from the dimension tables toward `FactBooking`.

For example:

```text
DimHotel
   ↓
FactBooking
```

This allows a selection such as **Resort Hotel** in a slicer to filter the related booking records while avoiding unnecessary reverse-filter paths.

Single-direction filtering was selected to reduce the possibility of ambiguous filter paths and to maintain a clear Star Schema structure.

---

## 7. Dedicated Date Table

The `DimDate` table was created as a dedicated Date dimension because the project requires analysis across different time periods.

The main active date relationship connects:

`DimDate[DateKey]`

to:

`FactBooking[ArrivalDateKey]`

This allows date attributes such as year, quarter, month, and week to filter booking records consistently.

The original arrival date components were combined during Power Query into an `Arrival Date` field, from which `ArrivalDateKey` was subsequently created for the relationship with `DimDate`.

The `reservation_status_date` was retained separately because it represents a different business event from the arrival date: it records the date associated with the final reservation status. It was therefore not treated as a replacement for the booking arrival date.

---

## 8. Appropriate Data Types

Key fields were created using numeric whole-number data types so that corresponding primary and foreign key fields use compatible types.

Examples include:

* `HotelKey` → Whole Number
* `CountryKey` → Whole Number
* `RoomKey` → Whole Number
* `MarketSegmentKey` → Whole Number
* `DateKey` → Whole Number
* `ArrivalDateKey` → Whole Number
* `Arrival Date` → Date
* `ADR` → Decimal Number
* Booking counts and numerical attributes → Whole Number where appropriate

Using compatible data types for relationship fields ensures that the keys can be matched correctly and supports reliable filtering and analysis.

---

## 9. Clear Table and Field Naming

The model uses descriptive and consistent names so that the purpose of each table and field is clear.

Examples include:

* `FactBooking`
* `DimHotel`
* `DimCountry`
* `DimRoom`
* `DimMarketSegment`
* `DimDate`
* `HotelKey`
* `CountryKey`
* `RoomKey`
* `MarketSegmentKey`
* `ArrivalDateKey`
* `Total Stay Nights`
* `Cancellation Status`

The original staging query, `hotels`, remains separate from the analytical model and is not loaded as a final model table.

---

## 10. Modelling Decisions and Challenges

One modelling challenge was deciding which fields should become dimensions and which should remain as attributes within the fact table. Not every categorical field was converted into a separate dimension. Dimensions were created only where they provided clear analytical value and supported the project's business questions.

The `agent` and `company` fields were also excluded from the final analytical model. Although they were handled during the Power Query cleaning stage, they were not central to the project's analytical objectives, and `company` contained a very high proportion of missing values. Removing them from the final model reduced unnecessary complexity while retaining the fields required for the planned analysis.

Another modelling decision involved the room fields. `reserved_room_type` was used to create `DimRoom`, while `assigned_room_type` remains in `FactBooking`. This preserves the distinction between the room originally requested and the room ultimately assigned.

The original `hotels` table was also kept as a staging query rather than loaded into the final model. This avoids duplicating the fact data and ensures that the final model is based on a clear Star Schema.

---

## Model Structure

The final analytical model therefore consists of:

![Completed Power BI Data Model](https://github.com/ibtj21/DSA3050-PowerBI-Hana-670555/blob/main/screenshots/03_model/completed_model%20_view.png)

The resulting model provides a structured foundation for the next stages of the project. The dimension tables provide descriptive and filtering context, while `FactBooking` provides the transactional booking data and measures that will be used to develop the project's **DAX calculations, KPIs, visualizations, and business insights**.

## *Transition to DAX*

With the analytical model established, the next stage is to develop **DAX measures and calculated indicators** using the relationships and filter context provided by the model. These measures will then feed the Power BI visualizations and dashboards used to investigate booking demand, cancellation behaviour, pricing, customer segments, and other business questions identified earlier in the project.

# SECTION D: DAX & BUSINESS CALCULATIONS

DAX measures were developed on top of the analytical data model to convert the cleaned booking data into meaningful business indicators. A total of **13 meaningful measures** were created, covering core KPIs, derived business measures, and advanced analytical calculations.

## Level 1 – Core Measures

### 1. Total Bookings

```DAX
Total Bookings =
COUNTROWS(FactBooking)
```

Counts the total number of booking records in `FactBooking`. This provides the primary volume measure used throughout the analysis.

### 2. Cancelled Bookings

```DAX
Cancelled Bookings =
CALCULATE(
    [Total Bookings],
    FactBooking[is_canceled] = 1
)
```

Calculates the number of bookings that were cancelled by applying a cancellation filter to the total bookings measure.

### 3. Completed Bookings

```DAX
Completed Bookings =
[Total Bookings] - [Cancelled Bookings]
```

Calculates bookings that were not cancelled by subtracting cancelled bookings from total bookings.

### 4. Average ADR

```DAX
Average ADR =
AVERAGE(FactBooking[adr])
```

Calculates the average Average Daily Rate (ADR) for the current filter context.

### 5. Total Nights

```DAX
Total Nights =
SUM(FactBooking[Total Stay Nights])
```

Calculates the total number of nights represented by all booking records in the current filter context. The underlying `Total Stay Nights` value was created earlier during Power Query from weekday and weekend stay nights.

---

## Level 2 – Calculated Business Measures

### 6. Cancellation Rate %

```DAX
Cancellation Rate % =
DIVIDE(
    [Cancelled Bookings],
    [Total Bookings],
    0
)
```

Calculates the proportion of bookings that were cancelled. `DIVIDE()` safely handles cases where the denominator is zero.

### 7. Average Lead Time

```DAX
Average Lead Time =
AVERAGE(FactBooking[lead_time])
```

Calculates the average number of days between booking and the scheduled arrival date.

### 8. Average Stay Nights

```DAX
Average Stay Nights =
AVERAGE(FactBooking[Total Stay Nights])
```

Calculates the average length of stay per booking.

### 9. Repeat Guest Rate %

```DAX
Repeat Guest Rate % =
DIVIDE(
    CALCULATE(
        [Total Bookings],
        FactBooking[is_repeated_guest] = 1
    ),
    [Total Bookings],
    0
)
```

Calculates the percentage of bookings made by repeat guests. `CALCULATE()` filters the booking records to repeat guests before the result is divided by total bookings.

### 10. Estimated Booking Revenue

```DAX
Estimated Booking Revenue =
SUMX(
    FactBooking,
    FactBooking[adr] * FactBooking[Total Stay Nights]
)
```

Estimates room revenue by multiplying ADR by total stay nights for each booking and summing the results. This is treated as an **estimated revenue proxy** because the dataset does not contain a directly recorded revenue field.

---

## Level 3 – Advanced DAX

### 11. Hotel Booking Rank

```DAX
Hotel Booking Rank =
RANKX(
    ALL(DimHotel[Hotel]),
    [Total Bookings],
    ,
    DESC,
    DENSE
)
```

Ranks hotels according to their total booking volume. `RANKX()` and `ALL()` allow the calculation to compare hotels against the complete hotel set rather than ranking only the currently filtered hotel.

### 12. Booking Share %

```DAX
Booking Share % =
DIVIDE(
    [Total Bookings],
    CALCULATE(
        [Total Bookings],
        ALLSELECTED(DimHotel[Hotel])
    ),
    0
)
```

Calculates the selected hotel's share of bookings while preserving other report-level selections. `ALLSELECTED()` enables comparison with the selected hotel context while retaining relevant external filters.

### 13. YoY Booking Growth %

```DAX
YoY Booking Growth % =
VAR CurrentBookings =
    [Total Bookings]
VAR PreviousYearBookings =
    CALCULATE(
        [Total Bookings],
        SAMEPERIODLASTYEAR(DimDate[Date])
    )
RETURN
    DIVIDE(
        CurrentBookings - PreviousYearBookings,
        PreviousYearBookings,
        0
    )
```

Calculates year-over-year growth in booking volume. The measure uses variables, `CALCULATE()`, `SAMEPERIODLASTYEAR()`, and `DIVIDE()` to compare the current period with the equivalent period in the previous year.

---

# Summary of DAX Measures

|  # | Measure                     | Level   | Main Purpose                         |
| -: | --------------------------- | ------- | ------------------------------------ |
|  1 | `Total Bookings`            | Level 1 | Total booking volume                 |
|  2 | `Cancelled Bookings`        | Level 1 | Number of cancelled bookings         |
|  3 | `Completed Bookings`        | Level 1 | Number of non-cancelled bookings     |
|  4 | `Average ADR`               | Level 1 | Average daily room rate              |
|  5 | `Total Nights`              | Level 1 | Total nights across bookings         |
|  6 | `Cancellation Rate %`       | Level 2 | Proportion of cancelled bookings     |
|  7 | `Average Lead Time`         | Level 2 | Average booking lead time            |
|  8 | `Average Stay Nights`       | Level 2 | Average booking duration             |
|  9 | `Repeat Guest Rate %`       | Level 2 | Share of bookings from repeat guests |
| 10 | `Estimated Booking Revenue` | Level 2 | Estimated room-revenue proxy         |
| 11 | `Hotel Booking Rank`        | Level 3 | Hotel ranking by booking volume      |
| 12 | `Booking Share %`           | Level 3 | Hotel contribution to total bookings |
| 13 | `YoY Booking Growth %`      | Level 3 | Year-over-year booking growth        |

The 13 measures exceed the required minimum of 12 and provide a progression from fundamental KPIs to more advanced analytical calculations.

---

# Documentation of the Six Most Important DAX Measures

The following six measures were selected as the most important because together they provide the core performance, cancellation, pricing, customer, and time-based indicators required for the hotel booking analysis.

## 1. Total Bookings

**What it calculates:**
`Total Bookings` counts the number of booking records in `FactBooking`.

**Why it is useful:**
It provides the fundamental measure of booking demand and acts as the denominator for several other calculations, including cancellation rate, repeat guest rate, and booking share.

**Main DAX functions:**
`COUNTROWS()`

**Filter context:**
The measure responds automatically to filters from dimensions such as hotel, country, room type, market segment, and date. For example, selecting `City Hotel` limits the count to City Hotel bookings.

**Dashboard use:**
Used as a primary KPI card and as the foundation for booking-volume visuals and other measures.

---

## 2. Cancelled Bookings

**What it calculates:**
Counts bookings where `is_canceled = 1`.

**Why it is useful:**
Cancellation volume is a major indicator of booking performance and helps management understand the scale of lost or cancelled demand.

**Main DAX functions:**
`CALCULATE()` and the existing `[Total Bookings]` measure.

**Filter context:**
The cancellation filter is applied within the existing report context. Selecting a hotel, country, month, or market segment calculates cancelled bookings specifically for that selection.

**Dashboard use:**
Used in KPI cards, cancellation comparisons, and cancellation-related charts.

---

## 3. Cancellation Rate %

**What it calculates:**
The percentage of bookings that were cancelled:

`Cancelled Bookings ÷ Total Bookings`

**Why it is useful:**
A rate is more informative than a raw cancellation count when comparing hotels, markets, countries, or periods of different sizes.

**Main DAX functions:**
`DIVIDE()`

**Filter context:**
The numerator and denominator are both evaluated within the current filter context. For example, selecting `Resort Hotel` returns the cancellation rate for Resort Hotel only.

**Dashboard use:**
Used as a major KPI and in visuals comparing cancellation behaviour across hotels, countries, market segments, and time periods.

---

## 4. Average ADR

**What it calculates:**
Calculates the average `adr` across booking records.

**Why it is useful:**
ADR is a key pricing indicator and allows management to compare the average daily rate across hotels, time periods, countries, market segments, and room types.

**Main DAX functions:**
`AVERAGE()`

**Filter context:**
The average changes dynamically according to the active report filters. For example, filtering to a particular hotel or month recalculates ADR for that subset.

**Dashboard use:**
Used in KPI cards and pricing comparison visuals.

---

## 5. Estimated Booking Revenue

**What it calculates:**
For each booking, ADR is multiplied by `Total Stay Nights`, and the resulting values are summed.

**Why it is useful:**
It provides an analytical estimate of room revenue and enables comparisons of revenue contribution across hotels, market segments, and time periods.

**Main DAX functions:**
`SUMX()`

**Filter context:**
`SUMX()` operates over the rows remaining in the current filter context. Therefore, selecting a hotel, country, or date period changes the estimated revenue accordingly.

**Dashboard use:**
Used in revenue-oriented KPI cards and comparison visuals.

---

## 6. YoY Booking Growth %

**What it calculates:**
Compares current booking volume with the equivalent period in the previous year and calculates the percentage change.

**Why it is useful:**
It helps identify whether booking demand is increasing or decreasing over time and provides a stronger performance indicator than a single-period booking count.

**Main DAX functions:**
`VAR`, `CALCULATE()`, `SAMEPERIODLASTYEAR()`, and `DIVIDE()`

**Filter context:**
The measure uses the dedicated `DimDate` table to shift the current date context to the previous year. Other active dimension filters, such as hotel or country, continue to affect the calculation.

**Dashboard use:**
Used in trend analysis and KPI visuals to show year-over-year changes in booking demand.

---

## DAX and Filter Context

The measures were designed to work with the Star Schema established in Section C. Dimension selections filter `FactBooking` through the one-to-many relationships, allowing the same DAX measure to produce different results according to the user's selections.

For example:

```text
DimHotel
   ↓
FactBooking
   ↓
DAX Measure
```

A measure such as `Total Bookings` therefore does not return one fixed number in every visual. Its result changes according to the active filter context created by slicers, axes, page filters, and other dimensions.

The use of `CALCULATE()`, `ALL()`, `ALLSELECTED()`, variables, `RANKX()`, and time intelligence demonstrates context manipulation and more advanced DAX techniques appropriate to the analytical model.

## *Transition to Data Visualization*

The DAX stage produced meaningful measures for analysing bookings, cancellations, pricing, guest behaviour, and performance trends. These measures now provide the foundation for the next stage: **interactive Power BI visualizations and dashboards**.


