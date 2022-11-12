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
The isinstance function returns True if the first argument is an instance of a certain class (or datatype such as int, float, etc.), or multiple classes:
```Python
isinstance(value,(class1,class2,...))
```
Use the type function to check the datatype of a variable:
```Python
type(variable)
```
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
### Sets
Sets are similar to lists, but they are unordered.

Create a set using:
```Python
{value1, value2, …}
```
To add a value to a set, use:
```Python
set_name.add(value)
```
To add multiple values to a set, use:
```Python
set_name.update({value1,value2,…})
```
To remove a value from a set, use:
```Python
set_name.remove(value)
```
The in and not in keywords can be used to check if a value exists within a set.

Set Comprehenrions work similarly to list comprehensions. For example, to create a set of the squared values from another set use:
```Python
{x**2 for x in set}
```
### Dictionaries
Dictionaries are "bags" of values each having their own label.

We index values in a dictionary using a “lookup tag”. Refer to a single value in a dictionary using:
```Python
dict_name[‘key’]
```
To access the value connected to a key, use the get function:
```Python
dict_name.get(‘key’, value_returned_if _key_does_not_exist)
```
Creating a dictionary:
```Python
dict_name = dict()
```
Add a key and value pair to a dictionary using:
```Python
dict_name[‘key1’] = value1
```
Use the in operator to see if a key exists in a dictionary:
```Python
‘key’ in dict_name
```
The update method works the same for dictionaries as it does for sets:
```Python
dict_name.update({‘key1’:value1,…})
```
#### Printing Dictionaries
Printing a dictionary will show each key and value combination in the dictionary:
```Python
print(dict_name)
# Result: {'key1':value1,'key2':value2,...}
```
To print only the keys, use:
```Python
print(dict_name.keys())
```
To print only the values, use:
```Python
print(dict_name.values())
```
#### Items Function
The items function will return the key and value combinations in separate tuples:
```Python
print(dict_name.items())
# Result: [('key1',value1),...]
```
We can use this to get two iteration variables during definite loops:
```Python
for key,value in dict_name.items():
  do this to the key and value
```
### Tuples
Tuples are similar to lists, but they are immutable (cannot be changed).

Create a tuple using:
```Python
(value1,value2,…)
```
The copy method does not work for tuples, but you may equate a variable to	another tuple. This variable may still not be changed.

We cannot sort tuples, but we can sort lists of tuples, such as those created using the items function on a dictionary:
```Python
sorted(dictionary.items(),Reversed=True/False)
```
## Classes
We can define all possible objects under a class by listing the characteristics and behaviors they can have.

An instance is one particular object that belongs to a class. The attributes of an instance are its state.

An object’s abilities are referred to as its methods. They are called using:
```Python
object.method_name()
```
Define a class using:
```Python
class class_name:
```
Construct an object which belongs to a class using:
```Python
object = class_name()
```
Constructors and Destructors: Optional functions defined inside of a class:
```Python
def __init__(self):
  # some operation
def __del__(self):
  # some operation
```
These functions are called when an instance of a class is created or destroyed.

Subclasses are more specialized versions of a class which inherit attributes and methods from parent classes.

Define a subclass using: 
```Python
class subclass_name(class_name):
```
## Constants
Constants are fixed values such as numbers, letters, or strings. Their values do not change.

“None” type is a constant and indicates “emptiness” and is used as a flag.

Defining a complex number:
```Python
variable = 4 + 5j
```
Booleans Values: True and False.

Use the int, float, and str functions to convert values from one datatype to another:
```Python
int(value)
float(value)
str(value)
```
## Variables
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
Delete an object or variable using:
```Python
del variable
```
If you run a calculation without assigning the value to a variable, the value is automatically assigned to the variable “_”.

Show all of the functions we can use to transform a variable using:
```Python
dir(variable)
```
## Operators
Operators: 
- '+'
- '-'
- '/'
- '*'
- '**'
- '%'

Comparison Operators: 
- '<'
- '<='
- '=='
- '>'
- '>='
- '!='

Boolean Operators: 
- not
- and
- or
- in
- is
- ==
- !=

0 == 0.0 is True. 0 is 0.0 is False. Use *is* when checking for Boolean and None types.

Use *and* and *or* to make more complex boolean operations.

The not function is used to reverse the outcome of a boolean operation:
```Python
x = True
y = not(x)
# Result: y = False
```
## Conditional Steps
Conditional steps are lines of code that only run if a specific condition or group of conditions is met.

Defined using if, elif and else statements:
```Python
if x < 10:
  do this
elif x > 20:
	do this
else:
	do this
```
If the code reaches a *pass* statement, the code will simply continue. It is used in place of	future or missing code sections.
## Repeated Steps
Repeated steps have iteration variables that change throughout each loop, and keep running while a condition is True.

For example, this code will run until n is equal to 10:
```Python
while n < 10:
	do this
	n = n + 1
```
If a loop contains a *break* statement and the code reaches this statement, the code willvjump to the code immediately following the loop.

If the code reaches a *continue* statement in a loop, it will jump to the next iteration.
## Definite Loops
Definite loops run the loop for each of the items in a set:
```Python
for variable in set_name:
	do this to variable
```
We can include an else statement after a for loop to execute if the for loop executes in its entirety without reaching a break statement.
## Try/Except
Use the try/except structure to prevent dangerous pieces of code from breaking the program:
```Python
try:
	try to do this
except:
	if the first try resulted in an error, do this and continue
```
## Functions
Functions take arguments and perform operations on them to return an output. Can be built-in or user designed.

Call functions using:
```Python
function_name(value1,value2, …)
```
or by defining each parameter:
```Python
function_name(parameter1 = value1, parameter2 = value2,...)
```
Using the second method allows you to rearrange the order in which arguments are defined when calling a function.

To apply a function to each value in an iterable, use:
```Python
variable = map(function_name, iterable_variable)
```

### Built-In Functions
Statistical Functions include:
- Min
- Max

The round function rounds a value to a certain number of decimal places:
```Python
round(value, number_of_decimal_places)
```
The divmod function outputs the quotient and the remainder in a tuple:
```Python
divmod(value1,value2)
```
The pow function raises the first argument to the power of the second	argument. If a third argument is included, the computed value will then be divided by the third argument, and the remainder will be output:
```Python
pow(value1,value2,value3)
```
The third value is optional.

The range function returns a list of numbers ranging from zero to one less than the parameter:
```Python
range(value)
```
This is useful when using for loops.

To create an object using the range function, use:
```Python
list(range(values))
```
Take input from users using:
```Python
input(‘Input Prompt’)
```
This function always returns a string.

To find the documentation of a function, type the function, followed by a	question mark:
```Python
function_name?
```
The help function achieves the same purpose:
```Python
help(function_name)
```
### Custom Functions
User-Created functions must be defined before they are called.

Defined using:
```Python
def function_name(parameter1, parameter2,...):
	do this
	return something
```
To allow a function to accept any number of arguments, use:
```Python
def function_name(*arg_name):
	for j in range(arg_name):
		do this
```
To accept any number of arguments while assigning specific key names to each argument, use:
```Python
def function_name(**arg_name):
```
Then, call this function using:
```Python
function_name(arg1 = value1, arg2 = value2, …)
```
To define a default value for an argument, which will be used if an argument is	not given when a function is called, use:
```Python
def function_name(default_value_name = default_value)
```
#### Modules
Instead of copying and pasting functions from one python file to another, we can use functions that are saved on a module. 

Modules are python files that contain specific functions that we plan to use in more than one python file.

Modules must be imported into each python file where you want to use it.

Import a module using:
```Python
import sys
sys.path.append(‘C:/MODULE FOLDER/’)
import module_name as new_name
```
Renaming the file is optional.

You can now use the functions in the module:
```Python
module_name.function_name(arguments)
```
Instead of importing the whole module, you can also import specific functions:
```Python
from module_name import function_name
```
## Importing Data
Base Python can be used to read csv and text files.

Open a file with:
```Python
with open(‘file_name.csv/txt’, ‘r’) as new_file_name:
```
Read each line using:
```Python
with open(‘file_name.csv/txt’, ‘r’) as new_file_name:
for index, line in enumerate(new_file_name.readlines()):
```
Each line in the file is given an index number, starting with 0.

The contents of each line are stored in a string, line.
### csv module
If the CSV file uses a character other than commas as the delimiter, we will use the csv module:
```Python
import csv
with open(‘file_name.csv/txt’, ‘r’) as new_file_name:
reader = csv.reader(new_file_name, delimiter = “delimiter”)
next(reader)	# Skips the Header. This is only necessary if one exists
for index, values in enumerate(reader):
if not values:
continue	# Skips empty lines
# The data for each line is stored in values.
# We can get each delimited part of values using:
part1, part2, … = values
```
