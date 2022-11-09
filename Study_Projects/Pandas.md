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
## Data Frames
