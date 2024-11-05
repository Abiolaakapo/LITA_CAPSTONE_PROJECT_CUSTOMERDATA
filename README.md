
### LITA_CAPSTONE_PROJECT_CUSTOMERDATA
This project aims to uncover customer data for a subscription company, study customer behaviour  and track subscription types. It also involves identifying key trends in cancellations and renewals to help make an informed and meaningful decisions.

### Project Title: Customer Segmentation For A Subscription Service

### Project Overview
This project dataset provides a comprehensive details of customer subscription trends and revenue, enabling insight as to why there are cancellations which on the long helps decision making.

### Column Description
- CustomerID: This is a unique identifier of each customer.
- CustomerName: This refers to the name of the customer.
- Region: The geographical location where subscribers resides.
- Subscrsiption Type: This refers to the bundle or the subscription plan available for customers such as Basic, Premium and Standard.
- SubscriptionStart: This the start date of the subsciption plan.
- SubscriptionEnd:  This the end date of the Subscription plan.
- Cancelled: The termination of customer's subscsription plan.
- Revenue: This the total amount generated from all subscribers.

### Tools Used
  Microsoft Excel
  - For Data Cleaning.
  - For Data Analyzing.
  - For Data Visualization.

  SQL: For Querying of Data.

  Power BI
 - For Data Tranformation.
 - Data Cleaning.
 - Data Visualization.

 ### Data Cleaning And Preparations
 The following action was carried out at the initial stage of data cleaning and Preparations.
 - Data loading and transformation.
 - Data Cleaning and Formatting.
 - Handling missing Variable.

 ### Exploratory Data Analysis
  The following are some of the analysis that was carried out.
  - Retrieve the total number of customers from each region.
  - Find the most popular subscription type by the number of customers.
  - Find customers who cancelled their subscription within six months.
  - Calculate the average subscription duration for all customers.
  - Find customers with subscription longer than twelve months.
  - Calculate total revenue by subscription type.
  - Find top three regions by subscription cancellations.
  - Find the total number of active and cancelled subscriptions.

    ### Data Analysis
    The data analysis was carried out using some select statements in SQL to query the data, Excel functions was used to calculate values 
    such as Basic, Premium, Standard and total revenue generated while Power BI was used to visualize the data using DAX functions.

   ```SQL 
    SELECT * FROM [dbo].[LITA_CUSTOMERR_DATA]

DELETE FROM [dbo].[LITA_CUSTOMERR_DATA]
WHERE REGION IS NULL


..........RETRIEVE THE TOTAL NUMBER OF CUSTOMER FROM EACH REGION.......

SELECT REGION,
COUNT(CustomerID) AS Total_Customers
FROM [dbo].[LITA_CUSTOMERR_DATA]
GROUP BY REGION

........MOST POPULAR SUBSCRPTION TYPE BY THE NUMBER OF CUSTOMER.........

SELECT Top 1 SubscriptionType,
COUNT(CustomerID) AS TotalCustomers
FROM [dbo].[LITA_CUSTOMERR_DATA]
GROUP BY SubscriptionType


..........CUSTOMER WHO CANCELLED THEIR SUBSCRIPTION WITHIN 6MONTHS...........
SELECT CustomerID,Canceled
FROM [dbo].[LITA_CUSTOMERR_DATA]
WHERE (Canceled)<=6
GROUP BY CustomerID,Canceled


..........AVERAGE SUBSCRIPTION FOR ALL CUSTOMERS.............
SELECT AVG(Datediff(Month,SubscriptionStart,SubscriptionEnd)) AS Average_Subscription
FROM [dbo].[LITA_CUSTOMERR_DATA]


............SUBSCRIPTION LONGER THAN 12 MONTHS..............
SELECT CustomerID
FROM [dbo].[LITA_CUSTOMERR_DATA]
WHERE Datediff(Month,SubscriptionStart,SubscriptionEnd)>12


.........TOTAL REVENUE BY SUBSCSRIPTION TYPE
SELECT SubscriptionType,
SUM(Revenue) AS Total_Revenue
FROM [dbo].[LITA_CUSTOMERR_DATA]
GROUP BY SubscriptionType


..........TOP THREE REGION BY SUBSCRIPTION CANCELLATIONS.........
SELECT TOP 3 Region,
COUNT(SubscriptionEnd) AS Canceled
FROM [dbo].[LITA_CUSTOMERR_DATA]
WHERE SubscriptionEnd IS NULL
GROUP BY Region 


....... TOTAL NUMBER OF ACTIVE AND CANCELLED SUBSCRIPTTION.......
SELECT CustomerID,
COUNT(SubscriptionStart) AS Active_Customer
FROM [dbo].[LITA_CUSTOMERR_DATA]
GROUP BY CustomerID


SELECT CustomerID,
COUNT(Canceled) AS Canceled
FROM [dbo].[LITA_CUSTOMERR_DATA]
GROUP BY CustomerID
```

### Data Visualization














### Results


  




    
   
  
