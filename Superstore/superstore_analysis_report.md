# Superstore Analysis Report
When I first decided to familiarize myself with data analysis techniques, I decided to analyze a public dataset. The dataset I used can be found on [Tableau Public's website](https://public.tableau.com/app/resources/sample-data) and it includes data regarding the products, sales and profits of an imaginary superstore. This document describes the process I took when analyzing this data and the results of my analysis.
## The Data
The data was borrowed from Tableau's collection of sample data. After downloading the file and opening it in Excel, I noticed that there were three sheets, titled *Orders*, *Returns*, and *People*. The *Orders* sheet contains information regarding 9994 orders made from the superstore. This includes information regarding: 
- Relevant dates
- Customers
- Products
- Sale Prices, Discounts and Profits

The *Returns* sheet includes a list of Order ID numbers. There is not a description describing what this information means, and I am not able to contact the person who provided the information, so I will assume this sheet provides a list of the orders which were returned to the superstore. The *People* sheet has four names, each of which is attributed to a region. I must assume that these are meant to be the names of people in charge of overseeing orders from each region.
## Goals
Before I could begin analyzing the data, I needed to determine what questions I wanted to answer using the data. After reviewing the information provided by the data, I decided to answer these questions:
1. Which kinds of products are returned most frequently?
2. Do we make a larger profit on average from repeat customers, or from customers who place a single order? 
3. Do repeat customers recieve more frequent and/or larger discounts than single order customers?
4. Do we make a larger profit on orders containing a larger number of items?
5. Do we make a larger profit off of our more expensive products?
6. Which cities are many of our orders sent to? 
7. What kinds of products are sent to which cities most frequently?
8. Which cities do we make a largest profit from?
9. Of the four regions, which makes the largest profit?
10. Which product categories are the most profitable? 
11. Which products within each category are the most profitable?
12. Which products are ordered more frequently using discounts? 
13. How large are the discounts on orders of certain products?
14. Has the superstore seen more orders in recent years? 
15. Has the superstore seen more profit?

While there are many more questions that this data could be used to answer, I believe that answering these questions will provide valuable insight into areas where the company could improve or capitalize on certain situations. Along with answering these questions, I will look for other valuable insights that this data can provide.
## Preparing the Data
Now that I know what I am looking for in the data, I can decide what data is necessary and what format it needs to be in. The data in the *Returns* sheet is valuable for answering the first question. However, I could instead use the information from the *Returns* sheet to create a column in the *Orders* sheet that describes which orders were returned, and then delete the *Returns* sheet. I did so using Excel's *COUNTIF* and *IF* functions. Now, a *Returned* column exists in the *Orders* sheet, showing *Yes* where an order was returned and *No* where it was not. Before I deleted the *Returns* sheet, I copied the *Returned* column and pasted it back in as the values only, rather than as a function. Then, I deleted the *Returns* sheet, and we now have the information on orders and returns on the same sheet.

The data in the *People* sheets can be left in that sheet since I only used it for quick references when deciding what to do once we answer question 9. I needed the product ID's, categories, sub-categories, and names for our analysis, so these columns were kept as is. We also need the names and ID's of customers, but we did not need the segment information for each order, so I deleted the *Segment* column. In terms of the financial aspects of each order, we need the sale price, quantity, discount, and profit for each. 

By creating a pivot table with the Countries as the rows, it becomes clear that each order is shipped within the United States. Knowing this, I deleted the *Country* column, since this information is already known for each order. Instead of having cities and states, separated, we can now combine the information into a single column, *City/State* using the *CONCATENATE* Excel function. The postal code did not seem relevant to my analysis, so I removed this column as well. The *Region* column was kept, since its information is relevant to answering question 9. My analysis does not rely on information regarding how the orders were shipped to the customers, so I deleted the *Ship Mode* column. Now, the geographical information for each order is prepared.

Both the order date and the ship date are provided, but for my analysis, I used the order date to answer questions 14 and 15. I deleted the *Ship Date* column, because it is no longer relevant. The *Row ID* column is not useful for my analysis, so I deleted this column as well, but kept the *Order ID* column, as it describes which products were placed in the same order.

By taking these steps, I made the data easier to understand and work with during the rest of my analysis.
## Cleaning the Data
Before we can perform a reliable analysis of our data, we must make sure that it is cleaned. 

The first step I took toward cleaning the data was rounding the values in the *Sales* and *Profit* columns to two decimals places, as monetary values should be. I do so by creating another column and using Excel's *ROUND* function. I then replaced the original columns with the new rounded columns. Next, I created a pivot table of the discount values in order to confirm that each was a reasonable value (between 0 and 1). I then did the same for the *Quantity* column.

While I cannot reliably confirm that each entry in the *Product Name* column is correct, I can do so for the *Category* and *Sub-Category* columns. I did so by creating a pivot table with the sub-categories as child rows to the categories. This revealed that there were no incorrectly entered values in these columns.

Two columns which I thought were going to be difficult to clean were the *Order ID* and *Product ID* columns. However, I decided to startby splitting each into separate parts, since each ID was separated into three parts using dashes. The order IDs contained either *US* or *CA* first, then the year, and then the designated number. The product IDs contained an abbreviation for the product category and an abbreviation for the sub-category, and then the designated number. Using the *LEFT*, *RIGHT* and *MID* Excel functions, I was able to separate these parts into six different columns. I then used a pivot table to confirm that each contained appropriate values. 

I then performed the same confirmation for the *Customer ID* column using the same method. Along with checking the customer ID's, I needed to check the customer names. To do so, I used the Excel *IF* and *FIND* functions to check whether the first and second letters of the customer IDs matched the customer's initials. After doing so, the first letters returned no errors, but the second letters returned a *#VALUE!* error in the pivot table. After looking further, I discovered that one person's name was entered as "Corey-Lock" and their customer ID began with "Co" rather than with two capital letters. Since I did not have a first name for this person, I could simply remove the dash in their name and used the two parts of their last name to remake their customer ID. Before doing so however, I used a pivot table to check if any other customer IDs began with "CL", to avoid confusing Corey-Lock's ID with another if they also somehow shared the same designated number in their ID. Other customer IDs did begin with "CL", so I filtered the data for all orders containing these customer ID's and created a pivot table to see which ID numbers were given to these customers. Corey-Lock's ID number did not match any of theirs, so I simply removed the dash in his name and changed all entries of his ID so they began with "CL". After doing so, no errors were returned in our pivot table for the names of the customers.

Next, I created a pivot table of the *City/State* column and browsed through it to see if there were any inappropriate entries, of which I did not find any. Doing the same for the *Region* column, I saw that there were only entries with the four available regions: *East*, *Central*, *South* and *West*.

Next, I created a pivot table for the *Order Date* column and found that each entry was a date between January of 2014 and December of 2017.

Finally, all of the data has been cleaned. Now, I can begin exploring the data in search for valuable information.
## Creating a Database
While working with the data, I noticed that there were many ID columns that described each unique item of a certain type. Because of this, I decided that it may be useful to create a database that contained all of this information. However, there were several problems with doing so. The first was that many orders containined multiple different products. I could display this information in a database, but it would be difficult to then use the JOIN feature of SQL to create complex queries. Another problem was that within each order, different products recieved different discounts and were purchased in idfferent quantities. It would not be efficent to attempt to describe this information within a database. The last problem I noticed was that many customers placed orders from several different locations, so we could  not assign each customer to a single location. 

Instead, I decided to create several database tables with information that was able to be effectively contained within a database. Originally, I intended to pair each product with its unit price, unit cost, and profit on purchases without a discount, but after reviewing the data, there seems to be inconsistencies in the calculations for the sale price of each order, as the unit price before discounts is often calculated as several different values for different orders of the same product. Because of this, I decided to simply include the non-monetary product information in the database. The database tables are described below:
1. Orders
  - Order ID
  - Order Date
  - City/State
  - Customer ID
  - Sale Total
  - Profit
  - Returned
2. Customers
  - Customer ID
  - Customer Name
3. Locations
  - City/State
  - Region
4. Products
  - Product ID
  - Category
  - Sub-Category
  - Product Name

I used pivot tables in Excel to gather the necessary information for  each table and then saved each sheet as a separate CSV File. Next, I needed to use a [Jupyter Notebook](https://github.com/p-grant/data_analysis_portfolio/blob/main/Superstore/Superstore_SQL_Tables_Preparation.ipynb) to rearrange the pivot table data into tables that can be uploaded into a SQL database. Next, I downloaded the four new files containing my database-ready tables. I then uploaded these tables to a [BigQuery Database](https://console.cloud.google.com/bigquery?project=superstore-367312&ws=!1m4!1m3!3m2!1ssuperstore-367312!2sSuperstore). 

Now that the database has been created, I am finally  able to begin my analysis.
## Analyzing the Data
### Returns Analysis
The first question I had regarding the data was about the products that were being returned. There were several pieces of information I wanted to derive from the data:
- At what rate does each product get returned?
  - Is there a similar characteristic of the products that have the highest return rates?
- Which product has been returned the most?
- Which product categories are returned most frequently?
- Which product sub-categories are returned most frequently? 

To begin this analysis, I needed a list of the products which have been returned. To do so, I gathered the Excel data on the products and returns for each order, and filtered out the data that was not returned. I then deleted the *Returned* column, so I had a list of each product that was returned. Next to this list, I included a list of each product purchased in all orders. I then used a [Jupyter Notebook]() to analyze the data.

The first insight from this analysis was a list of the return rates for each product. This list contains the return data for all products that have been returned at least one time. Products that have never been returned are not included in this list, as we already know that their return rate is 0%. The data can be found [here](data_analysis_portfolio/Superstore/Superstore_Return_Rates.csv).
## Visualizing the Data
