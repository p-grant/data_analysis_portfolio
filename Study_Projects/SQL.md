# SQL
Relational database: A database that contains a series of related tables that can be connected via their relationships.

Normalization: A process of organizing data in a relational database.

Types of Keys:
- Primary keys: An identifier that references a column in which each value is unique.
- Foreign keys: A field within a table that's a primary key in another table.
- Composite Key: A primary key constructed using multiple columns.

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
