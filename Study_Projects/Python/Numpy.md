# Python's Numpy Package
Numpy is a popular package for numerical python.

To import, use:
```Python
import numpy as np
```
## Arrays
Numpy allows you to create arrays, which are like lists, but contain data of all the same	type. These can be created using the array method as a list or tuple:
```Python
variable = np.array([1,2,3,4])
variable = np.array((1,2,3,4))
```
To specify the data type of an array, use:
```Python
np.array(values, dtype = ‘type’)
# types: Integer = ‘i’, Float = ‘f’, etc.
```
To determine the data type of an array, use:
```Python
variable.dtype
```
We can create multi-dimensional arrays. For example, to create a two-dimensional array, use:
```Python
a = np.array([[1,2,3],[4,5,6]])
```
To index a multi-dimensional array, you must index the larger dimensions first. For example, to index the value "3" from the previous array, use:
```Python
a[0,2]
```
We can determine the dimensions of an array using:
```Python
variable.ndim
```
This will output the number of indexes required to access a single value from the array.
### Shape
The shape method returns a tuple defining each dimension of an array:
```Python
variable.shape
```
With our array "a", this will output:
```Python
a.shape
# Result: (2,3)
```
Indexing the shape method tells us the elements in a certain dimension:
```Python
a.shape[1]
# Result: 3
```
The reshape method lets you redefine the dimensions of an array. For example, we can go from one dimension to two:
```Python
b = np.array([1,2,3,4,5,6])
c = b.reshape(2,3)
# Result: c = [[1,2,3]
    				   [4,5,6]]
```
### Size
The size method tells us the total number of elements in an array. The size of "a" is:
```Python
a.size
# Result: 6
```
### Array Functions
To create an array containing all zeros, use the zeros method:
```Python
np.zeros(number_of_zeros)
```
The ones method performs a similar function.

To create an array containing all of the same value, use the full method:
```Python
np.full(shape_of_array, value)
```
To do this while matching the shape of another array, use the full_like method:
```Python
np.full_like(array, value)
```
To repeat an array inside of a new array, use the repeat method:
```Python
np.repeat(array, number_of_repetitions, axis=0/1)
```
The arange method lets you create an array containing a range of values:
```Python
np.arange(100)
# Result: [0,1,2,…,99]
```
To define the starting number and end numbers of the range, use:
```Python
np.arange(10,20)
# Result: [10,11,12,…,19]
```
To define the gap between each element in the range, use:
```Python
np.arange(10,20,2)
# Result: [10,12,14,16,18]
```
This works similarly to the range function, except the range function does not create an object, it instead iterates through a list of numbers.

To create an array of numbers between two numbers, use the linspace method:
```Python
np.linspace(first_number,last_number,number_of_values_in_array)
```
Use the sort method to sort an array:
```Python
variable.sort(axis = axis_to_sort_by)
```
The hstack method allows us to concatenate two arrays horizontally (horizontal stack). The vstack method allows us to concatenate two arrays 
vertically (vertical stack):
```Python
np.hstack((array1,array2))
np.vstack((array1,array2))
```
Use the nan method to represent a missing value in an array:
```Python
np.nan
```
This returns a value similar to python’s None value.
## random Package
The random Package a subpackage inside of numpy.

The random.permutation method randomly rearranges the elements of an	array:
```Python
np.random.permutation(array)
```
The random.randint method generates a random integer:
```Python
np.random.randint
```
To define the lowest number, maximum number, and number of values	to generate, use:
```Python
np.random.randint(minimum,maximum+1,number_of_values)
```
The random.rand method generates a list of values between 0 and 1:
```Python
np.random.rand(number_of_values)
```
To define the shape of the matrix, use:
```Python
np.random.rand(2,3)
```
This will generate a 2 by 3 matrix.

The random.randn method generates a random list of numbers according to	gaussian distribution (they appear like the bell shaped curve):
```Python
np.random.randn(number_of_values)
```
## Indexing
To index several elements in an array, use a list of the element indexes inside the	index array:
```Python
variable1 = np.array([1,2,3,4,5,6])
variable2 = variable1[[1,3,5]]
# Result: variable2 = [2,4,6]
```
To index certain elements in an array, you can also use boolean data:
```Python
variable1 = np.array([1,2,3,4,5,6])
variable2 = variable1[[True,True,False,False,True,True]]
# Result: variable2 = [1,2,5,6]
```
## Slicing
Slicing in Numpy allows us to access subarrays of larger arrays.

Works similarly to slicing lists and strings.

However, differently from lists and strings, when we equate a variable to a slice	of another array and then change the values in our variable, the array will be
changed as well.

We did not make a copy of the array by equating a slice of it to a variable. Instead, we gave the variable a view of the array.

To make a copy of the slice of the array, use the copy method. This will allow you to change the variable without affecting the original array.

To slice a multidimensional array, use commas to separate dimensional indexes	while indexing each dimension as you would normally.
## Mathematics
To create an array folling a sine or cosine curve, use:
```Python
np.sin(array_to_curve_over)
```
To use the value of pi in an equation, use:
```Python
np.pi
```
To create an identity metrix, use the identity method:
```Python
np.identity(number_of_ones)
```
To multiply two matrices, use the matmul method:
```Python
np.matmul(matrix1, matrix2)
```
To transpose a matrix (two-dimensional array), use the T method:
```Python
array.T
```
Statistical Functions:
- The sum method calculates the sum of an array. 
- The mean method calculates the average. 
- The std method calculates the standard deviation. 
- The var method	calculates the variance.

For each, we can specify an axis over which to perform the calculation over:
```Python
array.sum(axis=0/1)
```
If axis = 0, the calculation will be done for each column. If axis = 1, it will	be done for each row.
### linalg Package
The linalg Package is Numpy’s linear algebra package.

To calculate the determinate of a matrix, use the det method:
```Python
np.linalg.det(matrix)
```
## Comparing Arrays
Comparison operators can be used with arrays.

For example, to find the elements in an array greater than 3, use:
```Python
variable1 = np.array([1,2,3,4,5])
variable2 = (variable1 > 3)
# Result: variable2 = [False, False, False, True, True]
```
The &/and and |/or keywords can also be used.

The where method lets you create an array based on a comparison operation. For example, we can set elements in an array greater than 2 equal to 0:
```Python
variable1 = np.array([1,2,3,4,5])
variable2 = np.where(variable1 > 2, 0, variable1)
# Result: variable2 = [1, 2, 0, 0, 0]
```
Use the argwhere method to find the indices where an array meets a certain condition:
```Python
np.argwhere(condition)
```
## Broadcasting
Using broadcasting in Numpy, we are able to make changes to each element in an array without creating another array:
```Python
variable = [1,2,3,4]
variable = variable + 5
# Result: variable = [6,7,8,9]
```
This also applies when adding arrays together, as long as the dimensions of each array allow it.





