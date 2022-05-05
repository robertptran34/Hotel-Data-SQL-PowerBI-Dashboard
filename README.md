# Hotel-Data-SQL-PowerBI-Dashboard

## 1. Overall Project Objectives
- Create a Power BI Dashboard sourced from a SQL database that has imported hotel revenue data downloaded from absentdata.com that will answer sample stakeholder questions:
  1. Is hotel revenue growing by the year?
  2. Should parkingh lot size be increased?
  3. What trends can be seen in the data?

## 2. Description of Data
- Tables:
  - dbo.'2018$': Table containing hotels 2018 revenue data. 
  - dbo.'2019$': Table containing hotels 2019 revenue data. 
  - dbo.'2020$': Table containing hotels 2020 revenue data. 
  - dbo.market_segment$: Table containing the factor value of discount applied relative to market segment.
  - dbo.meal_cost$: Table containing the cost value of relative meals. 
- Fields:
  - stays_in_week_nights: Float defining the amount of weeknights stayed. 
  - stays_in_weekend_nights: Float defining the amount of weekendnights stayed. 
  - adr: Float defining the average daily rate of hotel.
  - discount: Float defining the factor of discount applied. 
  - Revenue: Project created float showing the total revenue of hotel. Equals to ((stays_in_week_nights + stays_in_weekend_nights) / (adr * discount))
  - Total Nights: Project created float defining the total amount of nights hotels had stays. Equals to (sum(stays_in_week_nights) + sum(stays_in_weekend_nights))
  - hotel: Nvarchar(255), type of hotel.
  - arrival_date_year: Float, year of arrival at hotel. 
  - country: Nvarchar(255), country code of hotel. 
  - required_car_parking_spaces: Float, required parking space for stay. 
  - Parking Percentage: Project created float, percentage of parking space used. Equals to (sum(required_car_parking_spaces)/(Total Nights))
