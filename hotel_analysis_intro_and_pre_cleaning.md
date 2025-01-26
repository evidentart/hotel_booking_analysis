# Hotel Booking Analysis 

**Author:** Ali Akcin  

---

## Details of the Problem Our Proposed DSS Will Solve

The problem our proposed Decision Support System (DSS) will solve focuses on addressing inefficiencies in the hotel room booking process, which have led to lost revenue and customer dissatisfaction.  

Hotels often face challenges such as:
- Underutilized room inventory.
- Overbooking.
- Inconsistent pricing strategies.

These issues negatively impact the customer experience.  

Our DSS aims to:
- Use data to help hotel managers and staff make data-driven decisions on room pricing, occupancy forecasting, and booking management.
- Analyze historical booking patterns, customer behaviors, and pricing trends to optimize strategies.
- Enable real-time adjustments to pricing and inventory, improving room occupancy, preventing overbooking, and enhancing overall operational efficiency.

---

## Details of the Dataset

### Entities and Attributes

#### **Hotel**
- `hotel`: Type of hotel (resort or city).
- `meal`: Type of meal booked.
- `reserved_room_type`: Type of room initially reserved.
- `assigned_room_type`: Type of room assigned to guests.

#### **Booking**
- `is_canceled`: Indicates whether the booking was canceled or not.
- `lead_time`: Number of days between the booking date and the arrival date.
- `arrival_date_year`: Year of the arrival date.
- `arrival_date_month`: Month of the arrival date.
- `arrival_date_week_number`: Week number of arrival.
- `arrival_date_day_of_month`: Specific day of arrival.
- `stays_in_weekend_nights`: Number of weekend nights booked.
- `stays_in_week_nights`: Number of weeknights booked.
- `adults`: Number of adults in the booking.
- `children`: Number of children in the booking.
- `babies`: Number of babies in the booking.
- `total_of_special_requests`: Total number of special requests made.
- `booking_changes`: Number of changes made to the booking.
- `days_in_waiting_list`: Number of days on the waiting list.
- `adr`: Average daily rate (price per room).
- `required_car_parking_spaces`: Number of parking spaces required.

#### **Guest**
- `country`: Country of origin for each guest.
- `is_repeated_guest`: Indicates whether the guest is a repeated visitor.
- `previous_cancellations`: Number of previous cancellations by the guest.
- `previous_bookings_not_canceled`: Count of previous bookings not canceled.
- `customer_type`: Type of customer (e.g., transient, contract, group).

#### **Agent**
- `agent`: ID of the travel agency that made the booking.
- `company`: ID of the company that made the booking.

#### **Reservation Status**
- `reservation_status`: Status of the reservation (e.g., canceled, checked-in, no-show).
- `reservation_status_date`: Date on which the reservation status was last updated.

#### **Market Segment**
- `market_segment`: Various market segments that individuals belong to when making reservations.
- `distribution_channel`: Different channels through which bookings were made (e.g., online travel agencies, direct bookings).

### Summary
This dataset contains:
- **Records:** Over 119,391.
- **Columns:** 33.  

The dataset provides an overview of booking behavior and trends. Key attributes include:
- Booking date.
- Hotel type.
- Arrival date.
- Duration of stay.
- Number of guests.
- Country of origin.
- Distribution channels.
- Reservation status.  

While not all records and columns may be used, attributes like customer booking patterns, cancellations, and preferred rooms can help identify trends that could affect future marketing and booking strategies.

---

## Data Pre-Processing Performed

### Introduction
This section outlines the processes involved in data consolidation, cleaning, transformation, and reduction while working with hotel booking data. The primary tools used were:
- **PostgreSQL** for database management.
- **Tableau** for data visualization.

### Data Consolidation
1. Data was sourced from Kaggle and stored as a CSV file.
2. A PostgreSQL database was created to store the data.
3. A suitable table structure was designed in PostgreSQL, considering appropriate data types for each column.


-	Database connection and import of excel file
  
      ![Picture1](https://github.com/user-attachments/assets/7ba24285-74a0-40cf-940e-abd7fba44e1d)

-	Creation of tables and validating
  
      ![Picture2](https://github.com/user-attachments/assets/125e601a-f6ad-4cbe-9ec2-a75795adc102)

-	Creation of tables and validating
  
      ![Picture3](https://github.com/user-attachments/assets/38fcd671-8e28-47c2-a7a2-7f020b24493a)

- The data was sourced from a single CSV file, structured and altered as needed before being successfully imported into the PostgreSQL database without the need for merging
 
     ![Picture4](https://github.com/user-attachments/assets/054270cf-681d-49c3-a0ac-ceb7700a423c)


### Data Cleaning
- Missing values were identified and addressed in columns such as:
  - `country`: 488 missing entries were replaced with "Not Specified."
  - `agent` and `company`: Similar cleaning methods were applied.
- Data types were reviewed and adjusted for compatibility:
  - `adr`: Set as a decimal type.
  - `is_canceled`: Treated as a boolean.

      ![Picture5](https://github.com/user-attachments/assets/2268b4aa-c0f4-440f-b9aa-81dbe5c816e7)

### Data Transformation and Reduction
- Normalized columns where necessary, focusing on `adr` (average daily rate).
- Used SQL queries to calculate normalized values and identify outliers in numerical columns (`adr`, `lead_time`).
- Filtered out irrelevant columns and applied sampling methods to streamline the dataset.
- Handling null values in a dataset
  
    ![Picture6](https://github.com/user-attachments/assets/1deb2635-9f79-492c-8b1f-04a0d35278ca)

-	 Data Reduction random sampling

       ![Picture7](https://github.com/user-attachments/assets/cdb80a47-f787-4f2a-8893-f82d96594cf0)

-	 Data Reduction stratified sampling
	 
        ![Picture8](https://github.com/user-attachments/assets/dfc13dd5-d765-4d04-b7c0-f09707cd88e2)




-	 Analyzing the mean and median of profit is valuable for understanding overall profitability and identifying trends without being skewed by outliers. Mean ( 101.8311)

      ![Picture9](https://github.com/user-attachments/assets/c7f5d2fd-5643-4909-b5f8-ac72b9d88eb8)
 	 
-	Median (94.575)
  
      ![Picture10](https://github.com/user-attachments/assets/abde38d8-bcf5-482d-99f5-2d5aea36a585)

---

## Data Pre-Cleaning Process

Before diving into the detailed analysis and insights, the data underwent a comprehensive pre-cleaning process to ensure its integrity and readiness for analysis. Here's an overview of the steps taken:

### Initial Examination
- Conducted an exploratory data analysis to identify patterns, outliers, and anomalies.
- Calculated basic statistical measures such as mean, median, and standard deviation to understand the central tendency and dispersion.

### Data Cleaning with WEKA
- Utilized WEKA tools to preprocess the data, identifying and rectifying any inconsistencies or errors in the dataset.
- Addressed possible SQL code issues to enhance data quality and consistency.
- Applied various data cleaning techniques, including handling missing values, outlier detection, and normalization.

### Experimental Approach
- Employed an experimental methodology, iteratively refining data preprocessing techniques to ensure the highest level of data accuracy and reliability.
- Experimented with different data transformation methods, including various Python approaches, to uncover the most effective approach 

---

