# AdventureWorks Sales Analytics Dashboard

## Project Overview
This project analyzes sales performance for AdventureWorks, a fictional bicycle manufacturing company.  
The interactive dashboard was built using Power BI to explore product performance, customer behavior, and regional sales trends.

The project demonstrates an end-to-end Business Intelligence workflow including data cleaning, data modeling, DAX calculations, and dashboard development.

---

## Tools Used
- Power BI
- Power Query
- DAX
- Excel

---

## Dataset
The project uses the AdventureWorks dataset which contains information about sales transactions, return transactions, products, customers, and territories.

The data was cleaned and transformed using Power Query before building the data model and creating the dashboard.

---

## Dashboard Pages

### Executive Dashboard
Provides a high-level overview of business performance including revenue, profit, orders and sales trends.

### Maps
Visualizes geographical distribution of total orders to identify high-performing regions.

### Product Detail
Analyzes monthly profit, monthly revenue, monthly orders, revenue, profit and return rate trends for each product.

### Customer Dashboard
Provides insights into customer purchasing behavior and high-value customers.

---

## Key Measures

Some of the important DAX measures used in this project include:

 1. Total Revenue = 
 SUMX(
    'Sales Data',
    'Sales Data'[OrderQuantity] *
     RELATED('Product Lookup'[ProductPrice]
    )
 )

 2.Previous Month Revenue = 
  CALCULATE(
    [Total Revenue],
    DATEADD(
        'Calendar Lookup'[Date],-1,MONTH
        )
  )

 3. 10 day Rolling Revenue = 
   CALCULATE(
     [Total Revenue],
     DATESINPERIOD(
        'Calendar Lookup'[Date],
        MAX('Calendar Lookup'[Date]),-10,DAY
    )
  )

 4. YTD Revenue = 
   CALCULATE([Total Revenue],DATESYTD('Calendar Lookup'[Date])) 

 5. Bulk Orders = 
       CALCULATE(
    	  [Total Orders],'Sales Data'[OrderQuantity] >1
       ) 

 6. Bikes Return = 
      CALCULATE(
        [Quantity return],
        'Product Categories Lookup'[CategoryName] = "Bikes"
      )


---

## Key Insights

• Mountain 200 Black generated the highest revenue among all products.

• United States emerged as the strongest sales country by number of orders.

• Customers in the 'Average' income level contribute highest (46.1 %) of all orders among all income level category.

• Customers in the 'Professional' occupation contribute highest (43.41 %) of all orders among all occupation category.


---

## Author

Aashish Rohila