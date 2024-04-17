# Uber_Modelling_Data_Warehouse

- [Description](#description)
- [Dataset](#Dataset)
- [Modelling](#Modelling)
- [Data Transfer Process](#Data_Transfer_Process)
- [DWH Design](#DWH_Design)
   - [Star Schema](#Star_Schema)
   - [Diagram](#Diagram)
- [Tools](#Tools)


## Description

- The project aims to design and implement a data warehouse for Uber data using star schema modeling. This involves creating dimensions and a fact table to facilitate efficient data analysis and reporting. The final step is to transfer the modeled data from a CSV file to a Data Warehouse in MS SQL Server.

## Dataset

- The TLC Trip Record Data encompasses trip details for both yellow and green taxis, containing essential fields such as pick-up and drop-off timestamps, locations, travel distances, fare breakdowns, rate categories, payment methods, and passenger counts reported by drivers.

- More info about dataset can be found here:
     - https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page
     - https://www.nyc.gov/assets/tlc/downloads/pdf/data_dictionary_trip_records_yellow.pdf


## Modelling

1) Star Schema Design on Draw.io:
   
   - Utilized Draw.io for visualizing the star schema design.
   - Designed dimensions including Dim_DataTime, Dim_Passenger_Count, Dim_Trip_Distance, Dim_Rate_Code, Dim_Payment_Type, Dim_Dropoff_Location, and Dim_Pickup_Location.
   - Created a fact table named Fact_Table_Merged representing Uber trip data.
   - Creating Dimensions in Python DataFrame

3) Implemented dimensions in Python using pandas DataFrame:
  - Each dimension contains unique identifiers and relevant attributes for analysis.
  - Ensured data consistency and integrity within each dimension.

3) Creating Fact Table:
  - Constructed a fact table named Fact_Table_Merged by merging relevant dimensions with Uber trip data.
  - Ensured referential integrity by linking foreign keys from dimensions to the fact table.

## Data_Transfer_Process

1) Data Extraction:
   - Imported Uber trip data from a CSV file into pandas DataFrame.

2) Data Modeling and Transformation:
  - Modeled the data into dimensions and fact table using Python pandas.
  - Renamed columns, handled data types, and ensured data quality.

3) Data Loading into MS SQL Server:
   - Established a connection to the MS SQL Server using Windows authentication.
   - Created tables for dimensions and the fact table in the Data Warehouse.
   - Transferred the modeled data from pandas DataFrames to MS SQL Server using SQLAlchemy's create_engine function.

## DWH_Design

### Star Schema
![Demo Sample](https://github.com/Sandra-Essa/Uber_Modelling_Data_Warehouse/blob/main/Media/Modelling%20Schema.drawio.png)

### Diagram
![Demo Sample](https://github.com/Sandra-Essa/Uber_Modelling_Data_Warehouse/blob/main/Media/Modelling%20Schema.png)

## Tools

1. Python
2. Jupyter Notebook
3. Draw.io
4. Libraries: Pandas, pyodbc
5. MS SQL Server
