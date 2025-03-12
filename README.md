# NYC Taxi ETL 🚖

![ETL Workflow](https://github.com/John-Wassef/NYC-Taxi-ETL/blob/main/NYC%20Taxi%20ETL.png)

## Project Overview  
This project is an **ETL (Extract, Transform, Load) pipeline** built using **Talend** to process **NYC Taxi data for January 2024**. The pipeline extracts raw taxi trip data, performs **data cleaning and transformation**, and loads the cleaned dataset into a **PostgreSQL database**.

🔹 **Dataset Source:** [NYC Taxi Trip Records](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)  
🔹 **Data Dictionary:** [Yellow Taxi Data Dictionary (PDF)](https://www.nyc.gov/assets/tlc/downloads/pdf/data_dictionary_trip_records_yellow.pdf)  

---

## Data Cleaning & Transformation 🛠️  
✔ **Removed null values** and invalid data (e.g., trips with distances < 0.1 km).  
✔ **Added new calculated columns:**  
   - `trip_distance_in_minutes`  
   - `average_speed_in_mph`  
✔ **Enhanced location details:**  
   - `PUZone` (Pickup Zone) & `PUBorough` (Pickup Borough)  
   - `DOZone` (Dropoff Zone) & `DOBorough` (Dropoff Borough)  
   - Joined with `zone_lookup` table on **Location ID**.  
✔ **Refactored categorical values for better usability:**  
   - **RateCodeID → RateCodeType**  
     ```
     1 = Standard rate
     2 = JFK
     3 = Newark
     4 = Nassau or Westchester
     5 = Negotiated fare
     6 = Group ride
     ```
   - **Store_and_fwd_flag (Y/N) → (1/0)** (for easier ML use).  
   - **Payment_type → Meaningful values:**  
     ```
     1 = Credit card
     2 = Cash
     3 = No charge
     4 = Dispute
     5 = Unknown
     6 = Voided trip
     ```
✔ **Loaded the final clean dataset into a PostgreSQL database.**  

---

## Technology Stack 🏗️  
- **Talend Open Studio** (ETL)  
- **PostgreSQL** (Database)  
- **NYC Taxi Data** (Dataset)  

---

## How to Use ⚡  
1. **Clone the repository**  
   ```bash
   git clone https://github.com/John-Wassef/NYC-Taxi-ETL.git
