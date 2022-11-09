# Python's Pandas Package
Pandas is a popular and powerful data science python package.

Most of Numpy's features are included in Pandas.

Import using:
```Python
import pandas as pd
```
## Series
Series behave similar to python dictionaries, except Series are ordered.

Create a series using:
```Python
variable = pd.Series([value1,value2,…],index=['key1’,’key2’,…])
```
If the indices are not defined, the default indices are 0,1,2, etc.

We can also input a dictionary into the series method:
```Python
variable = pd.Series({‘key1’:value1,’key2’:value2,…})
```
Rename a series using:
```Python
series.name = “new series name”
```
This new name can be used later on to reference the series.

We can access the values and indices of a series using:
```Python
variable.values
variable.index
```
The values of this series form a numpy array.
### Slicing Series
Slicing using explicit indices:
```Python
variable[‘first_key’:’final_key’]
```
This is different from slicing other python objects, because the	final value in the index is included in the slice.

Slicing using implicit indices:
```Python
variable[first_index:final_index+1]
```
This is the same way we index other objects.

When using integers for your explicit indices, there may be confusion	when indexing your series:

- The following will index using explicit indices:
```Python
series[1]
```
- The following will index using implicit indices:
```Python
series[1:3]
```
To ensure that you index using explicit indices, use the loc method:
```Python
series.loc[1]
```
To ensure that you index using implicit indices, use the iloc	method:
```Python
series.iloc[1:3]
```
### Boolean Series
When a series contains boolean data types (True/False), we can use the sum and mean methods to count how many times True appears in the series:
```Python
series.sum()
series.mean()
```
The any and all methods are used to check the state of boolean data in a series:
```Python
series.any()
series.all()
```
For any, if any of the values in the series are True, this method will return True.

For all, if each value in a series is True, this method will return	True.
### Duplicates
We can use the duplicated method to show us the indexes of our series that contain duplicated values (values that appeared earlier in the series):
```Python
series.duplicated()
```
This will return True for all indices with duplicated values after the first.

If we want to reverse the order in which we look for duplicates in the	series, we will use the keep argument:
```Python
series.duplicated(keep=’last’)
```
This will return False for the last occurance of a value in a series,	and True for any duplicated values that appear before that.

If we want to identify all indicies that contain duplicate values, use:
```Python
series.duplicated(keep=False)
```
This will return True for all indicies with duplicated values.

The drop_duplicates method works the same way as the duplicated	method, but it will remove the values that returned True from the series:
```Python
series.drop_duplicates(keep=’last’/False)
```
### Missing Data
The dropna function will remove all missing (NaN) values from a series:
```Python
series.dropna()
```
## Data Frames
Data frames can be thought of as multi-dimensional pandas series.

Each series can be thought of as a column in a table, while the keys are the labels of each column.

Create a data frame using:
```Python
variable = pd.DataFrame({‘key1’:Series1,’key2’:Series2,…})
```
You can also input a list of dictionaries into the DataFrame method:
```Python
pd.DataFrame([dict1,dict2,…])
```
Each key will represent a column, and the rows will be ordered starting with 0.

To add a column to a data frame, use:
```Python
data_frame[‘column_name’] = Series/dictionary_to_be_added
```
To delete a column, use:
```Python
del data_frame[‘column_name’]
```
To delete multiple columns, use the drop method:
```Python
data_frame.drop([‘column1’,’column2’,…],inplace = True/False)
```
If inplace is False, this will create a temporary variable and not make the changes directly to the data frame.

To rename columns or rows in a data frame, use the rename method:
```Python
data_frame.rename(columns{‘original1’:’new1’,’original2’:’new2’,…}, index = {‘original_row1’:’new_row1’,…} ,inplace = True/False)
```
### Viewing Data Frames
To view the values in a data frame, use:
```Python
data_frame.values
```
To see the column names of a data frame, use:
```Python
data_frame.columns
```
To see the row names of a data frame, use:
```Python
data_frame.index
```
Use the head method to view the top rows of a data frame:
```Python
data_frame.head(number_of_rows)
```
Use the tail method to see the last rows of a data frame:
```Python
data_frame.tail()
```
To see an overview of the data, use the describe method:
```Python
data_frame.describe()
```
To see more information about the data frame, including the number of null-types and the data types in the	data, use the info method:
```Python
data_frame.info()
```
### Indexing Data Frames
To index the values in a data frame, use:
```Python
data_frame.values[row,column]
```
The rows and columns are indexed starting with 0.
### Data Frame Analysis
#### Transforming Data Frames
To transpose a data frame, use:
```Python
variable.T
```
To convert date type data to datetime data, use the to_datetime method:
```Python
pd.to_datetime(data_frame[‘column’])
```
The dates will be converted to the form:
```Python
yyyy-mm-dd
```
The reset_index method resets the index of a data frame:
```Python
df.reset_index()
```
#### Grouping by Columns
The groupby method is used to get summary of data related to specific values found in a	column:
```Python
data_frame.groupby(‘column_to_group_by’	)[[‘column_to_show1’,’column_to_show2’,…]].summary_function().reset_index()
```
The summary_function can be any function that performs a calculation based on	the data, such as sum, max, min, etc.

The reset_index resets the index of the new data frame.

To group by several columns, use:
```Python
data_frame.groupby([‘column1’,’column2’])…
```
Each combination of the two columns will be shown.

#### Filtering Data Frames
We can filter the data in a data frame. For example, we can filter the data to only see data where the grade is less than 90:
```Python
data_frame[data_frame[‘grade’]<90]
```
#### Missing Data in Data Frames
If a series in a data frame does not contain a value for an index in the data frame, NaN will be insert into the data frame.

To find missing values, or nan values, use the isnull or isna methods:
```Python
pd.isnull(value)
pd.isna(value)
```
These will return True where the value is missing. The notnull and notna methods do the opposite:
```Python
pd.notnull(value)
pd.notna(value)
```
To replace the NaN values with another value, use the fillna method:
```Python
data_frame.fillna(value_to_replace_na)
```
If you wish to replace missing values with the value that before or	after it, use the method argument:
```Python
data_frame.fillna(method=’ffill’,axis=0)
data_frame.fillna(method=’ffill’,axis=1)
```
Having axis=0 will fill the replace missing values with the one	before	it in that column.

Having axis=1 will replace missing values with the one after it in that row

To drop all rows that contain a NaN value, use the dropna method:
```Python
data_frame.dropna(0)
```
To drop all columns that contain NaN, use:
```Python
data_frame.dropna(1)
```
The count method can also be used to count the number of numeric values	in each row or column of a data frame:
```Python
data_frame.count(axis=’index’/’columns’,numeric_only = True/False)
```
The axis parameter defaults to ‘index’ if no value is given. If numeric_only is True, all non-numeric values will be counted as	well.
### Importing Data Frames
#### CSV Files 
Use the read_csv method:
```Python
data_frame = pd.read_csv(‘c:/PATH_TO_FILE/file_name.csv’)
```
In the read_csv documentation, there are many options for customizing how a file is read.

read_csv automatically treats the first row as a header. To tell it not to do	this, include header = None as an argument.

To then change the names of each column, use this argument:
```Python
names = [‘column1’,’column2’, …]
```
To specify the data type of a column, use the argument:
```Python
dtype = {‘column_name’: ‘data type’}
```
The kinds of data types are accepted as ‘float’, etc.

To change certain values into NaN values, you will include this argument:
```Python
na_values = [‘string1’,’string2’, …]
```
Instead of using to_datetime for each column needed in a date format,	we can use this argument:
```Python
parse_dates = [col_index1,col_index2, …]
```
To specify the delimiter being used in the CSV file, use this argument:
```Python
sep = ‘delimiter’
```
Instead of using a path to the file on your computer, you can also use a URL to a CSV file stored on a website.

To save a data frame as a CSV file:
```Python
data_frame.to_csv(‘file_name.csv’)
```
#### SQL
First, you must import the necessary module for the database program you use. For example, if using sqlite, use:
```Python
import sqlite3
```
Then, connect to the SQL file:
```Python
sql_file = sqlite3.connect(‘c:/PATH TO FILE/database_name.db’)
```
Then, query the file:
```Python
pd.read_sql(‘’’
SQL QUERY
;
‘’’, sql_file, index_col = ‘column_to_index_by’)
```
We can also use the parse_dates argument, using the column’s explicit	indicies.

To instead get a whole table from a database, use:
```Python
from sqlalchemy import create_engine
engine = create_engine(‘c:/PATH TO FILE/database_name.db’)
sql_file = engine.connect()
pd.read_sql_table(‘table_name’, con = sql_file)
```
To close the connection, use:
```Python
connection.close()
```
Exporting a data frame as a table into a SQL database:
```Python
data_frame.to_sql(‘table_name’,sql_file)
```
Before running this command, you should make sure the SQL database does not	already contain a table with this name.
#### Excel
Import Excel files using:
```Python
data_frame = pd.read_excel(‘file_name.xlsx’)
```
Like with reading CSV files, there are many arguments we can can use to	customize how excel files are read.

Exporting data to excel:
```Python
excel_file = pd.ExcelWriter(‘file_name.xlsx’)
Data_frame.to_excel(excel_file, sheet_name = ‘sheet_name’)
excel_file.save()
```
We can write multiple data frames to the same file by putting them in different	sheets.


