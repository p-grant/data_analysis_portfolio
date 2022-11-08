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
We can compare strings using comparison operators. The results depend on the alphabetical/numerical order of each consecutive character:
```Python
'apple' < 'banana'
'apple' > 'Apple'
'apple' > 'Banana'
```
Each of the comparisons above will return as True.

We can create a multiline string using:
```Python
variable = """first line,
second line,
third line"""
```
This will print exactly as written.

To print a string with quotation marks inside it, use the escape key:
```Python
“text \”text in quotations\” more text”
```
To make the string print to a new line, use:
```Python
“text \n text on new line”
```
To insert a tab into a string, use:
```Python
“text \t tabbed text”
```
To force a string to print without being affected by escape characters within it,	use:
```Python
r”text\new text”
```
This will print exactly how it is written.
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
If the second number is beyond the field of the string, it stops at the last value of the string.

By leaving off the first or last number of our slice index, we can look from the beginning or the end of the string.

For example, to access the first four values of a string, use:
```Python
string[:4]
```
We can also reverse the direction of our index by using negative numbers.

For example, to access the third-to-last and second-to-last values in a string, use:
```Python
string[-3:-1]
```
We can tell the index how often to return values using a third index number.

For example, to index every three values from the first eight values of a string, use:
```Python
string[:8:3]
```
One way to reverse a string is by using:
```Python
string[::-1]
```
#### String Functions and Methods
The split method is used to split strings into multiple values in a list:
```Python
string.split(‘delimiter’)
```
The len function tells us how many characters are in a string:
```Python
len(string)
```
The in and not in keywords are used to check if one string is or is not inside of another:
```Python
'substring' in string
'substring' not in string
```
This will return True if the substring is found inside the string.

The find method lets us find the position of a substring in a string:
```Python
string_name.find(‘substring’,position_to_begin_looking)
```
If the substring is not found, the function will return -1.

The replace method replaces all occurrences of a substring in a string with another substring:
```Python
string_name.replace(‘substring_to_replace’,’new_substring’)
```
The lstrip and rstrip functions remove whitespace to the left or right of a string. The strip function removes whitespace from the left and the right of a string:
```Python
lstrip(string)
rstrip(string)
strip(string)
```
The startswith method returns True if a string begins with a certain substring:
```Python
string.startswith(‘substring’)
```
Use the lower and upper methods to convert characters in a string to	upper or lowercase:
```Python
string.lower()
string.upper()
```
The capitalize method capitalizes the first letter, and makes the rest lowercase:
```Python
string.capitalize()
```
The count method counts the number of times a substring appears in a string:
```Python
string.count(“substring”)
```
We can convert a value into a string using the str function:
```Python
str(value)
```
### Lists
Lists are constants separated by commas and surrounded by square brackets:
```Python
variable = [0,"hello",2,3.5]
```
We can concatenate and split lists just like strings.

We can check if a value is in or is not in a string using the in and not in operators, just like with strings.

Lists are mutable, so we can change them using the index operator:
```Python
list[index] = a_value_or_list
```
Values in lists are indexed in the same way we index values in strings.

List Comprehensions: We can perform a calculation that affects each value in a list.

For example, to square every number in a list, use:
```Python
[i**2 for i in list]
```
Several functions take lists as parameters: max, min, sum, len.

If instead of making a copy, you equate two lists, any change made to one list will affect the other:
```Python
h1 = [1,2,3]
h2 = h1
h2[0] = 2
# Result: h1 = [2,2,3]
```
#### List Functions and Methods
We can create an empty list using the list function:
```Python
variable = list()
```
To remove every value from a list, use the clear method:
```Python
list.clear()
```
We can add a value to the end of a list using the append function:
```Python
list.append(value)
```
To remove and return a value from a list use the pop method:
```Python
list.pop(index)
```
If no index is provided, the default value will be the last in the list.

We can sort a string by using the sort function:
```Python
list.sort()
```
To reverse a list, use the reverse method:
```Python
list.reverse()
```
To make a copy of a list, use:
```Python
new_list = list.copy()
```
The copy method also works for dictionaries and sets. 
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

## Functions
The range function returns a list of numbers ranging from zero to one less than the parameter:
```Python
range(value)
```
This is useful when using for loops.

To create an object using the range function, use:
```Python
list(range(values))
```
