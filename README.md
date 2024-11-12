 # Capstone-Project-CustomerData1

### OUTLINE

[PROJECT TOPIC](#projecttopic)

[PROJECT OVERVIEW](#projectoverview) 

[COLUMN DESCRIPTION](#columndescription)

[DATA SOURCES](#datasource)

[TOOLS USED](#toolsused)

[DATA CLEANING AND PREPARATION](#datacleaningandpreparation)

[EXPLORATORY DATA ANALYSIS (EDA)](#exploratorydataanalysis)

[DATA ANALYSIS](#dataanalysis)

[DATA VISUALIZATION](#datavisualization)



### Project Topic: Customer Analysis

### Project Overview

This project overview provides insight into Customers subscription data, highlighting key trends like subscription growth,, Active subscribers, inactive sucscribers and the region where customers cancelled subscription, this allows us to know where to channel our marketing strategy


### Column Description
- CustomerID: A unique identfier for each Customer

- CustomerName: A distinct identifier for each customer

- Region: The geographical location (North, South, East, West)

 - SubscriptionType: The type of subscription subscribed to

- SubscriptionStart: The day subscription was renewed

- SubscriptionEnd: The day subscription expired

- Cancelled: The subscription that was cancelled

### Data Sources

The Data used was provided by Lita-Incubator-Hub for the purpose of Training and learning


![CustomerData Pivot](https://github.com/user-attachments/assets/326a702d-3194-4737-932b-847b51438100)

### Tools Used

- Microsoft Excel [Download Here](https://www.microsoft.com)
    1. For Data Cleaning
    2. For Analysis
    3. For Visualization

- SQL- Structured query Language for quering of Data

- Power BI: For Data Cleaning And Visualization

- GitHub for Portfolio Building

### Data Cleaning And Preparation

In the initial phase of the data cleaning and preparation, we perform the following actions;

1. Data loading and Inspection
2. Removing Duplicates
3. Data cleaning and Formating

### Exploratory Data Analysis (EDA)

EDA involved the exploration of the Data to answer some questions above the Data such as;

- retrieve the total number of customers from each region.
  
- find the most popular subscription type by the number of customers.

- find customers who canceled their subscription within 6 months.

- calculate the average subscription duration for all customers.

- find customers with subscriptions longer than 12 months.

- calculate total revenue by subscription type.

- find the top 3 regions by subscription cancellations.

- find the total number of active and canceled subscriptions


### Data Analysis

This is where we include  some basic lines of queries and some of the DAX expressions used during your analysis;

.....CUSTOMERSDATA PROJECT......


```
select * from [dbo].[CustomerDatacsv1]
```


1....Total number of customer from each region......


```
Select Region, Count(distinct CustomerID) As Total_Customer
From [dbo].[CustomerDatacsv1]
Group by Region
```


2.....Most popular subscriptype by number of customers

```
Select Top 1 subscriptionType, count(distinct CustomerID) As Total_Customer
from [dbo].[CustomerDatacsv1]
Group By subscriptionType
Order By total_Customer
DESC
```

3..... Customers who cancelled their subscription within 6 months....

```
Select CustomerID from  [dbo].[CustomerDatacsv1]    
where Datediff(month, subscriptionStart,SubscriptionEnd)<=6
```

4.... Average subscription duration

```
Select AVG(datediff(day, SubscriptionStart, subscriptionEnd)) As Avg_Subscription_Duration
From [dbo].[CustomerDatacsv1]
```

5..... Customers with subscription longer than 12 months....

```
Select CustomerID
From [dbo].[CustomerDatacsv1]
Where Datediff(Month, SubscriptionStart,SubscriptionEnd)>12;
```

6.....Total Revenue by subscriptiontype.....

```
select Subscriptiontype, Sum(Revenure)As Total_Revenue
from [dbo].[CustomerDatacsv1]
Group By SubscriptionType
```

7.....Top 3 Region by subscription cancellation.....

```
Select Top 3 Region, count(*) as Subscriptionend_count
From [dbo].[CustomerDatacsv1]
Where Subscriptionend is Null
Group By Region 
```

8......Total number of active and canceled subscription.....

```
Select Canceled, COUNT(*) As Subscription_Count
From [dbo].[CustomerDatacsv1]
Group By Canceled;
```


### Data Visualization


![CustomerData Pivot](https://github.com/user-attachments/assets/07218ec1-d882-4e4c-993d-cc93a0060f9c)




![CustomerData PowerBI](https://github.com/user-attachments/assets/16def6e6-39ba-49d9-a42c-2d2f1e79d976)








