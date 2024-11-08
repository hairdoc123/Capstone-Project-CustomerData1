# Capstone-Project-CustomerData1

### 
# Capstone-Project-SalesData1

### Project Topic: SalesData Analysis

### Project Overview

This project analysed the sales performance of a retail store, identify trends, sales performance of each products and the region that makes the highest sales.


### Column Description
- OrderID: A unique identfier for each order placed by a customer

- CustomerID: A distinct identifier for each customer placing order

- Region: The geographical location (North, South, East, West)

 - OrderDate: The date in which order was made

- Quantity: The number of item/product purchased for each product

- UnitPrice: The price per unit of the product

### Data Sources

The Data used was provided by Lita-Incubator-Hub for the purpose of Training and learning

![SalesData table](https://github.com/user-attachments/assets/f7a671f3-aad0-4c2e-8a6f-60ef139f989c)


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

- retrieve the total sales for each product category.
  
- find the number of sales transactions in each region.

- find the highest-selling product by total sales value.

- calculate total revenue per product.

- calculate monthly sales totals for the current year.
  
- find the top 5 customers by total purchase amount.
  
- calculate the percentage of total sales contributed by each region.
  
- identify products with no sales in the last quarter.

### Data Analysis

This is where we include  some basic lines of queries and some of the DAX expressions used during your analysis;
# Capstone-Project-SalesData1

### Project Topic: SalesData Analysis

### Project Overview

This project analysed the sales performance of a retail store, identify trends, sales performance of each products and the region that makes the highest sales.


### Column Description
- OrderID: A unique identfier for each order placed by a customer

- CustomerID: A distinct identifier for each customer placing order

- Region: The geographical location (North, South, East, West)

 - OrderDate: The date in which order was made

- Quantity: The number of item/product purchased for each product

- UnitPrice: The price per unit of the product

### Data Sources

The Data used was provided by Lita-Incubator-Hub for the purpose of Training and learning

![SalesData table](https://github.com/user-attachments/assets/f7a671f3-aad0-4c2e-8a6f-60ef139f989c)


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

![SaleData Charts](https://github.com/user-attachments/assets/e3194165-86e8-4658-a97b-2996566f6a06)


![SalesData Pivot](https://github.com/user-attachments/assets/856bc842-0bbc-4e27-8081-6bf25ded7af3)



![SalesData Power BI](https://github.com/user-attachments/assets/8182374a-d5b0-4273-959a-70a8c1b0fe47)






```

### Data Visualization







