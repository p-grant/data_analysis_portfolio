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

While there are many more questions that this data could be used to answer, I believe that answering these questions will provide valuable insight into areas where the company could improve or capitalize on certain situations.
## Preparing the Data
Now that I know what I am looking for in the data, I can decide what data is necessary and what format it needs to be in. The data in the *Returns* sheet is valuable for answering the first question. However, I could instead use the information from the *Returns* sheet to create a column in the *Orders* sheet that describes which orders were returned, and then delete the *Returns* sheet. I did so using Excel's *COUNTIF* and *IF* functions. Now, a *Returned* column exists in the *Orders* sheet, showing *Yes* where an order was returned and *No* where it was not. Before I deleted the *Returns* sheet, I copied the *Returned* column and pasted it back in as the values only, rather than as a function. Then, I deleted the *Returns* sheet, and we now have the information on orders and returns on the same sheet.

The data in the *People* sheets can be left in that sheet since I only used it for quick references when deciding what to do once we answer question 9. I needed the product ID's, categories, sub-categories, and names for our analysis, so these columns were kept as is. We also need the names and ID's of customers, but we did not need the segment information for each order, so I deleted the *Segment* column. In terms of the financial aspects of each order, we need the sale price, quantity, discount, and profit for each. 

By creating a pivot table with the Countries as the rows, it becomes clear that each order is shipped within the United States. Knowing this, I deleted the *Country* column, since this information is already known for each order. Instead of having cities and states, separated, we can now combine the information into a single column, *City/State* using the *CONCATENATE* Excel function. The postal code did not seem relevant to my analysis, so I removed this column as well. The *Region* column was kept, since its information is relevant to answering question 9. My analysis does not rely on information regarding how the orders were shipped to the customers, so I deleted the *Ship Mode* column. Now, the geographical information for each order is prepared.

Both the order date and the ship date are provided, but for my analysis, I used the order date to answer questions 14 and 15. I deleted the *Ship Date* column, because it is no longer relevant. The *Row ID* column is not useful for my analysis, so I deleted this column as well, but kept the *Order ID* column, as it describes which products were placed in the same order.

By taking these steps, I made the data easier to understand and work with during the rest of my analysis.

## Cleaning the Data
## Analyzing the Data
## Visualizing the Data
