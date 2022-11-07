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
## Comments
Use #... to write a comment in a line.
```R
# This will not affect my code
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
## Functions
Arguments are information R needs for a function to run.

Open the help page regarding a function:
```R
?function_name()
```
Print a text string or a variable’s value in the console:
```R
print(“text string”, “variable”)
```
Statistical Functions: We can calculate the mean, standard deviation, and correlation between two variables using the mean, sd, and cor functions.
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
## Conditional Statements
Conditional Statement are a declaration that if a certain condition holds, then a certain event must take place.

Written as:
```R
if (condition) {
  expression1
} else if (condition) {
  expression2
} else {
  expression3
}
```
## Logic
Logical Operators: Return a logical data type (TRUE/FALSE).

AND = & or &&. OR = | or ||. NOT = !.
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
## Data Frames
Data Frame: A collection of columns–similar to a spreadsheet or SQL table. Each column has a name at the top that represents a variable, and includes one observation per row.

To manually create a data frame in R, use:
```R
data.frame(column1 = c(value1, value2, …), column2 = c(value1, value2,…),…)
```
This function accepts vectors as inputs.

To make changes to a data frame, use the mutate function from the dplyr package:
```R
mutate(data_frame, new_column = calculation_which_can_include_other_columns)
```
To create a new data frame that includes columns from another, use the select function from the dplyr package:
```R
new_data_frame <- select(old_data_frame, column1, column2, …)
```
To select all columns except one column from a dataset, use:
```R
select(dataset, -column_to_exclude)
```
### Tibbles
Tibbles are streamlined data frames:
- Never change the data types of the inputs. 
- Never change the names of your variables. 
- Never create row names. 
- Make printing in R easier.

Create a tibble using:
```R
as.tibble(dataset)
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
You can use the “palmerpenguins” dataset to experiment with R.
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
## Cleaning Data
More useful packages for cleaning data:
- here
- skimr
- janitor

The skim_without_charts function can give us a summary of a dataset.

The rename function lets you rename a column in a dataset:
```R
rename(dataset, new_name1 = original_name1, new_name2 = original_name2,…)
```
The rename_with function renames column names to be more consistent. For example, we can change all letters in our column names to upper case:
```R
rename_with(dataset, toupper)
```
The clean_names function ensures that there are only characters, numbers and underscores in the names.

The summarize function lets us generate statistical summaries for a dataset. For example, we can calculate the mean of a column:
```R
summarize(dataset, mean_value = mean(column))
```
### Checking for Bias
The bias function finds the average amount that the actual outcome is greater than the expected outcome:
```R
bias(actual_values, predicted_values)
```
The further the result is from zero, the higher the chance is that the data is biased.

Install and load the “SimDesign” package to use the bias function.
## Organizing Data
The arrange, group_by and filter functions are useful for organizing our data.

When using arrange, we can sort by descending order by adding a “-“ sign before the column name.

When performing group level summaries, we can use the drop_na function to remove empty values from our calculation.

The group_by function is generally accompanied by other functions in order to perform statistical calculations.
## Transforming Data
The separate, unite and mutate functions are used to transform data.

The separate function splits one column into multiple:
```R
separate(data_frame, old_column, into = c(‘new column 1’, ‘new column 2’, …), sep = ‘desired_delimiter’)
```
The unite function lets us merge columns together:
```R
unite(data_frame, ‘new_column’, old_column1, old_column2, …, sep = ‘desired_delimiter’)
```
The mutate function can be used to add new columns to a data frame:
```R
mutate(data_frame, new_column = calculation_which_can_include_other_columns)
```
## Visualizing Data
The “ggplot2” package is useful for visualizing data in R.

Core concepts:
- Aesthetic: A visual property of an object in your plot.
- Geom: The geometric object used to represent your data.
- Facets: Let you display smaller groups, or subsets, of your data.
- Labels and Annotations: Let you customize your plot.

Create our visuals using the ggplot function. It creates a coordinate system that we can add layers to:
```R
ggplot(data = dataset)
```
You can add layers to your plot using “+”.
### Geoms
You can choose a geom by adding a geom function. geom_point, geom_bar and geom_line, geom_jitter,and geom_smooth are all used to create different plots. 

You can include multiple plot styles on your visual by including more layers using “+”.

Each geom function takes a mapping argument, defining how the variables in 	your dataset are mapped to visual properties. The mapping argument is always paired with the aes function.

The x and y arguments of the aes function specify which variables to map to the x and y axes of the plot:
```R
ggplot(data = dataset)+geom_point(mapping = aes(x = x_axis_data, y = y_axis_data))
```
The geom_jitter function creates a scatterplot and adds a small amount of random noise to each datapoint, allowing us to more easily see each data point when our plot is crowded.

When using geom_bar, if a variable is not mapped to the y aesthetic, R automatically counts how many times each unique value in the variable mapped to x appears in the data.

Smoothing: Enables the detection of a data trend even when you can't easily notice a trend from the plotted data points. There are two types:
- Loess: Best for smoothing plots with less than 1000 points.
```R
geom_smooth(method = “loess”)
```
- Gam: Best for smoothing plots with more than 1000 points.
```R
geom_smooth(method = “gam”, formula = y ~s(x))
```
### Aesthetics
We can change the color, shape, size, or the type of our graph to make it more appealing.
 	
To map an aesthetic to a variable, set the name of the aesthetic equal to the variable inside the parentheses of the aes function.

Mapping a variable to color will assign a different color to each unique value for that variable and create a legend. The same also works for shape, size, and alpha (transparency). We can also map the same variable to each:
```R
aes(…, color = variable)
```
To assign an aesthetic to the entire plot, we must define it outside of the aes function:
```R
aes(…), color = “color”)
```
For the smooth and line plots, we can include the linetype aesthetic inside the aes function and map it to a variable to create separate lines for each unique value for that variable.

Use the fill aesthetic to color the inside of each bar on a bar chart. The color aesthetic only adds a colored outline to each bar.

To add a color to specific bars, use:
```R
col = ifelse (condition, “color1”, “color2”)
```
Mapping a variable other than the one mapped to x for fill or color will create a stacked bar chart.
### Facets
There are two facet functions: facet_wrap and facet_grid.

facet_wrap lets us create separate plots for each unique value that is in a variable:
```R
facet_wrap(~variable)
```
facet_grid lets us create separate plots for each unique combination of values that belong to two variables:
```R
facet_grid(variable1~variable2)
```
### Annotations
Annotate: Add notes to a document or diagram to explain or comment upon it.

Lets us put text within our plot:
```R
annotate(“text”, x = position, y = position, label = “text_displayed”)
```
The “text” portion describes the type of label.

We can also change the color, font,size and angle of our text:
```R
annotate(…, color = “color”, fontface = “bold”, size = size_of_font, angle = degree_of_tilt)
```
Store the plot as a variable to use less code.
### Labels
Use the labs function to add labels to your plot. This lets us put text outside our plot.

Arguments:
- Titles: title = “title”
- Subtitles: subtitle = “subtitle”
- Captions: caption = “caption”
### Saving Plots
Two options: Export option, or ggsave function.
ggsave saves the last plot you created:
```R
ggsave(“filename.type”)
```
## R Markdown Files
R Markdown files allow you to put code and writing in the same place.

Markdown is a simple language for adding formatting to text documents.

Use the “knit” button to export your work into a readable document.

R Notebook: Lets users run your code and show the graphs and charts that visualize the code.

Installing R Markdown:
```R
install.packages(“rmarkdown”)
```
## Resources
- [RStudio Cheat Sheets](https://posit.co/resources/cheatsheets/)
- [RStudio Data Primers](https://rstudio.cloud/learn/primers/3)
- [Useful Packages](https://support.posit.co/hc/en-us/articles/201057987-Quick-list-of-useful-R-packages)
- [Dates and Times](https://rawgit.com/rstudio/cheatsheets/master/lubridate.pdf)
- [R Files Documentation](https://www.rdocumentation.org/packages/base/versions/3.6.2/topics/files)
- [Data Wrangling](http://statseducation.com/Introduction-to-R/modules/getting%20data/data-wrangling/)
- [ggplot2 Cheat Sheet](https://ggplot2.tidyverse.org/)
- [R Markdown](https://rmarkdown.rstudio.com/lesson-1.html)
