# R Programming
R is a programming language frequently used for statistical analysis, visualization and other data analyses.
## Using and Accessing Files
To create a new folder or directory to hold your files, use:
```R
dir.create(“folder_name”)
```
To create a blank file, use:
```R
file.create(“file_name.type”)
```
Typically, files will be in the form of a .txt, .docx, or .csv file.

To copy a file, use:
```R
file.copy(“file_name.type”, “destination_folder”)
```
Delete R files using:
```R
unlink(“file_name.type”)
```
## Variables
Variables (objects) are representations of values that can be stored for use later.

Variable names should start with a letter, and can contain numbers and underscores.

Use the assignment operator, <-, to assign a value to a variable.
## Vectors
Vectors are groups of data elements of the same type stored in a sequence in R.
The combine function lets you make a vector:
```R
c(x,y,z,…)
```
Atomic Vectors:
- Atomic vectors have values of all the same type.
- Four kinds in data analysis: 
  - Logical (True/False)
  - Integer (3,-5)
    - To insert integers into a vector, each value must be followed by “L”.
  - Double (1.4, 3.56)
  - Character (“text_strings”)

Lists:
- Lists are vectors that have values of different types. 
- Created using:
```R
list("a", 1L, 1.5, TRUE)
```
- The str() function tells you what types of elements a list contains.

To check the type of vector you are working with, use:
```R
typeof(vector)
```
To check how many values are in a vector, use:
```R
length(vector)
```
To check that a vector is a certain type use the following functions, which will return either True or False:
```R
is.logical
is.character
is.integer
is.double
```
After assigning a vector to a variable, we can assign a name to each value in the vector:
```R
names(vector) <- c(“name1”,”name2”,…)
```
Lists can be named using: 
```R
list('name1' = value1, 'name2' = value2, …)
```
We can see the value assigned to a name using:
```R
$name
```
## Matrices
Matrix: A two-dimensional collection of data elements.

Create a matrix using:
```R
matrix(vector, nrow/ncol = number_of_rows_or_columns)
```
## Pipes
Pipes are a tool in R for expressing a sequence of multiple operations, represented with “%>%”.

Using a pipe is essentially the same as writing “and then”.

Instead of using nested functions, we can use pipes.
```R
variable <- dataset %>%
  function1(arguments_other_than_dataset) %>%
  function2(arguments_other_than_dataset) %>%
  …
```
## Datasets
- To load an already installed dataset, use the data function:
```R
data(“dataset”)
```
  - By running the data function without an argument, we can see a list of the available datasets.
- View a summary of an object in the data:
```R
summary(object_name)
```
- View the data related to an object:
```R
View(object_name)
```
- Display the columns and the first several rows of data:
```R
head(dataset)
```
- Display a summary of the data horizontally:
```R
glimpse(dataset)
```
- Return each column name in a dataset:
```R
colnames(dataset)
```
## Packages
Install a package using:
```R
install.packages(“package_name”)
```
To see all installed packages, use:
```R
installed.packages()
```
To load a package, use:
```R
library(package_name)
```
CRAN (Comprehensive R Archive Network): An online archive with R packages, source code, 	manuals, and documentation.
### Tidyverse Packages
These are packages commonly used by data analysts.
The included packages are: 
- ggplot2
- tibble
- tidyr
- readr
- purrr
- dplyr
- stringr
- forcats

ggplot2 is used for data visualization.

dplyr helps complete some common data manipulation tasks:
- The select function picks variables based on their names.
- The filter function finds cases where certain conditions are true.
```R
filter(dataset, column == value)
```
- The arrange function lets us sort data by a specific column.	
```R
arrange(dataset, column_to_sort_by)
```
- The group_by function groups our results according to a certain column.
```R
group_by(dataset, column_to_group_by)
```
tidyr is useful for data cleaning:
- Wide and Long Data in R: 
  - The pivot_longer and pivot_wider functions (from the tidyr package) are used to convert data into long and wide formats in R.

readr is used to import data:
- Functions include:
  - read_csv
  - read_tsv
  - read_delim
  - read_fwf
  - read_table
  - read_log
- Example:
```R
readr_csv(“dataset.csv”)
```
- To use readr sample files, use the readr_example function:
```R
readr_example(“dataset.type”)
```
### Other Packages
The readxl package is used to import spreadhseet data into R:
- This must be loaded after loading tidyverse, because it is not a core tidyverse package.
- Use the read_excel function to load data from a spreadsheet:
```R
read_excel(“dataset.xlsx”, sheet = “sheet_name”)
```
  - Specific Sheets can be loaded by using the sheet property.

The lubridate package lets us work with dates and times:
- Dates: (“year-month-day”)
- Time within a day: (“hh:mm:ss UTC”)
- Date and Time: (“year-month-dd hh:mm:ss UTC”)
- To get the current date, use today(). To get the current date and time, use now().
- Use ymd_hms() to convert a string to a date-time.
  - Use only ymd to get a date. Use only hms to get a time. 
	- The order of each letter in the function can be swapped as needed.
	  - Letters can also be left out if their value is not in the string.
	- The dates in the strings being converted can show months as number, the month’s name, or as abbreviations of the month’s name.
## Comments
Use #... to write a comment in a line.
