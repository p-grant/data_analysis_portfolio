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
UPDATE table
SET column = ‘value 1’
WHERE column = ‘value 2’;
CREATE TABLE IF NOT EXISTS: Creates a new table in the database.
DROP TABLE IF EXISTS: Deletes a table from the database.
DELETE: Removes a row from a table.
DELETE table
WHERE column = ‘value’

