# SQL
Relational database: A database that contains a series of related tables that can be connected via their relationships.

Normalization: A process of organizing data in a relational database.

Types of Keys:
- Primary keys: An identifier that references a column in which each value is unique.
- Foreign keys: A field within a table that's a primary key in another table.
- Composite Key: A primary key constructed using multiple columns.

## Datatypes
SQL can work with several different datatypes:
- STRING
- INT (Positive or Negative Whole Numbers)
- FLOAT (Numbers with a Decimal)
- DATE
- DATETIME

## Working with Tables
INSERT INTO: Used to insert new data into a table:
```sql
INSERT INTO table
  (column 1, column 2, etc.)
VALUES
  (value 1, value 2, etc.);
```
UPDATE: Used to change a value in a table.
```sql
UPDATE table
SET column = ‘value 1’
WHERE column = ‘value 2’;
```
CREATE TABLE IF NOT EXISTS: Creates a new table in the database.

DROP TABLE IF EXISTS: Deletes a table from the database.

DELETE: Removes a row from a table.
```sql
DELETE table
WHERE column = ‘value’
```
## SQL Queries
Basic Structure of a SQL Query:
```sql
SELECT 
  column_1,
  column_2,
  etc
FROM 
  table
WHERE
  condition
```
When querying a table in BigQuery, use "dataset_name.table.name"

To select every column, use the \* symbol.
Example:

To show all columns from the movies table where the genre is action, use:
```sql
SELECT
  *
FROM 
  movies
WHERE
  genre = 'Action'
```
OR/AND logic can be used for more complicated queries:
```sql
WHERE
  col_1 > 5
  AND col_2 = 'One'
```
```sql
WHERE
  col_1 = 'Three'
  OR col_2 = 6
```
The <> operator is used as the "not equal to" operator.

To query data that match a specific pattern, use the LIKE clause. For example, we can query all data where the value begins with "Ch" and is followed by one or more random characters:
```sql
WHERE
  col_1 LIKE 'Ch%'
```
Some database systems use \* as the random character symbol instead of %.

Comments in SQL are text placed between "/\*" and "\*/" or after two dashes ("--"):
```sql
-- this will not affect the query
```
Aliases are used to more easily reference a column or table, instead of actually renaming them:
```sql
col_1 AS one
SELECT
  one
FROM
  table
```
## Cleaning Data with SQL
DISTINCT: Tells the database that we only want to see unique rows from the table. This helps us remove duplicate rows from our data:
```sql
SELECT
  DISTINCT column
```
LENGTH: Tells us the length of a text string in a table:
```sql
SELECT
  LENGTH(column)
```
SUBSTR: Used to return a portion of a text string:
```sql
WHERE
  SUBSTR(column,starting position, number of letters we want) = 'substring'
```
The first letter in a text string is at position 1.

EXTRACT(PART FROM date): Pulls one part of a given date to use.

TRIM: Removes extra spaces from a text string.

CAST: Converts anything from one data type to another:
```sql
CAST(column AS TYPE) 
```
ORDER BY: Sorts a column:
```sql
ORDER BY 
  column DESC/ASC
```
DESC: Sorts in descending order, ASC: Sorts in ascending order.

When sorting strings, we start with the first letter or number.

BETWEEN: Specifies a range from one value to another. Values can be numbers or dates:
```sql
BETWEEN 2 AND 8
```
```sql
BETWEEN '2020-12-01' AND '2020-12-31'
```
CONCAT: Combines text strings to create new text strings that can be used as unique keys:
```sql
CONCAT(column 1, column 2)
```
CONCAT_WS: Performs the same function as CONCAT, but places a separator in between each text string:
```sql
CONCAT_WS(‘separator’,text string 1, text string 2, text string 3,…)
```
COALESCE: Returns non-NULL values in a list:
```sql
SELECT
  COALESCE(column to check first, column to check second)
```
If the value of the first column is NULL, the value from the second column will be used instead.

COUNT: Counts the number of rows in a column:
```sql
COUNT(column)
```
To count the number of unique values in a column, use:
```sql
COUNT(DISTINCT column)
```
To create the equivalent of a pivot table by grouping the query according to avalue, use the GROUP BY command:
```sql
GROUP BY
  column1, column2, etc
```
HAVING: Filters your query rather than the table. Syntax is the same as with the WHERE clause. 

CASE: Goes through one or more conditions and returns a value when a condition is met. A  new column is created with the updated values:
```sql
CASE
  WHEN condition THEN new_value
  WHEN condition THEN new_value
  ELSE original_column
END AS new_column_name
```
IF: Used to replace certain values where a condition is met:
```sql
IF(
condition,
new_value,
original_column) AS new_column_name
```
You can find missing data by displaying data where a value is NULL.

## Subqueries
Execute before the query they rest inside of. They are usually nested in FROM or WHERE query clauses. Designated using parentheses:
```sql
SELECT
  (SELECT...
  FROM...)
```
## Statistical Functions
SUM: Calculates the sum of a column; AVG: Calculates the average value for a column:
```sql
SUM(column)
AVG(column)
```
ROUND: Used to round a value:
```sql
ROUND(value, number of decimal places)
```
MIN AND MAX: Return a column’s minimum and maximum values:
```sql
MIN(column)
MAX(column)
```
## JOINS
JOINS: A SQL clause that's used to combine rows from two or more tables based on a related column.	

Inner JOIN: A function that returns records with matching values in both tables. (Usually the default JOIN used by analysts):
```sql
JOIN
```
Left JOIN: Will return all the records from the left table and only the matching records from the right table:
```sql
LEFT JOIN
```
Right JOIN: Will return all the records from the right table and only the matching records from the left table:
```sql
RIGHT JOIN
```
(The table mentioned first is left, and the table mentioned second is right.)

Outer JOIN: Will return all records in both tables:
```sql
FULL OUTER JOIN
```
NULL will appear for values that don’t appear in one table, but appear in the other.

Example JOIN query:
```sql
SELECT
* 
FROM
table_1
JOIN 
table_2 ON
table_1.column = table_2.column
```
## Temporary Tables
Tables that are deleted after your session ends.

The WITH clause is a type of temporary table that you can query multiple times:
```sql
WITH temp_table_name AS (
  SELECT 
    columns
	FROM
	  table
	)
```
In the same query, we can now reference the new temporary table.

SELECT INTO: Copies data from one table into a new table but it doesn't add the new table to the database.

(BigQuery does not recognize SELECT INTO)

CREATE TABLE is useful when multiple people will use the same table.

## Resources
- [SQL Cheat Sheet](https://towardsdatascience.com/sql-cheat-sheet-776f8e3189fa)
- [W3 Tutorial](https://www.w3schools.com/sql/default.asp)
- [SQL Functions](https://www.w3schools.com/sql/sql_ref_sqlserver.asp)
- [SQL Keywords](https://www.w3schools.com/sql/sql_ref_keywords.asp)
