# Hotel-Data-SQL-PowerBI-Dashboard

## 1. Overall Project Objectives:
- Create a Power BI Dashboard sourced from a SQL database that has imported hotel revenue data downloaded from absentdata.com that will answer sample stakeholder questions:
  1. Is hotel revenue growing by the year?
  2. Should parking lot size be increased?
  3. What trends can be seen in the data?

## 2. Description of Data:
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

## 3. Project Plan:
A. Load all data in local SQL database. 

B. Query all necessary fields from various tables for dashboard. 

C. Connect SQL server query to Power BI interface.

D. Create new fields in Power BI that will assist in data visualization. 

E. Develop visual dashboard product that answers stackholder's questions. 

## 4. Project Progress:

![image](https://user-images.githubusercontent.com/100554707/166867863-5547f170-4f0f-45b9-a109-83dbbcaaa2bf.png)

- SQL Query used to pull specific data from tables into power BI. Selects all columns from 2018, 2019, and 2020 revenue data combined using union command and joins to market segment table on market_segment column as well as to meal cost table on meal column keeping all columns in the combined 2018, 2019, and 2020 tables and columns that exist in both combined table and the respective matching column of the market segment and meal tables as it is a left join operation. 

![image](https://user-images.githubusercontent.com/100554707/166868385-4b578718-e604-4915-aa5a-9d7110152dfd.png)

- Power BI dashboard created that shows the changes in revenue over time using a line plot as well as showing total revenue, average ADR with mini line plot, average discount with mini line plot, and car spaces with mini line plot.
- Bottom portion of dashboard shows revenue proportion by hotel in a donut plot with a pivot table listing revenue, parking space, parking percentage seperated and aggregated by hotel and year. 

![image](https://user-images.githubusercontent.com/100554707/166868657-e6dd4553-a6d6-4dbe-b055-eab7e2dcdcd5.png)

- Dashboard slicer that allows end user to adjust the dates included in the visual dashboards relative to data. 

![image](https://user-images.githubusercontent.com/100554707/166868674-46df4b59-0fb4-482e-a49b-600713b5f59e.png)

- Dashboard slicer that allows end user to adjust the hotel type included in the visual dashboards relative to data. 

![image](https://user-images.githubusercontent.com/100554707/166868692-f1eafa89-d255-4048-b267-add5a0707744.png)

- Dashboard slicer that allows end user to adjust the country included in the visual dashboards relative to data. 

## 5. Findings:

- From the dashboard we can see that revenue has been increased from 2018 to 2019 but dropped slightly in the 2020 year. There is also no compelling evidence that parking lot size should be increased as the hotel is only using about 2%-3% of parking spaces per year. We can see a trend of resort hotel's revenue increasing close to during the summer time spiking in July with an exception of 2020 while city hotels see revenue spikes around end of September. 
