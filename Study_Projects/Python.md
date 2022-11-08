# Python
## Comments
Use "#" at the beginning of a line to write a comment
```Python
# This will not affect my code
```
You can also write multi-line comments using:
```Python
"""
This will
not affect my code
"""
```
## Data Types
### Strings
Strings are sequences of characters within single or double quotation marks.

We can concatenate strings together using "+":
```Python
variable = "string one" + "string two"
```
#### Indexing Strings
A string can be indexed by using the string name followed by the index in brackets:
```Python
string_name[index]
```
The index of a string begins at zero.

For example, we can access the third value in a string using:
```Python
string[2]
```
#### Slicing Strings
We can look at a series of values contained in a string by using indexes.

For example, to look at the third, fourth and fifth values in a string, use:
```Python
string[2:5]
```
## Variables
Constants are fixed values such as numbers, letters, or strings. Their values do not change.

Variables are named places where we store data. Their values can change throughout a program.

Assign data to a variable using:
```Python
variable_name = value
```
You can assign values to multiple variables at the same time using:
```Python
variable1, variable2 = value1, value2
```
To see each variable stored in the memory, use:
```Python
%whos
```
If you run a calculation without assigning the value to a variable, the value is automatically assigned to the variable “_”.
