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
tidyr is useful for data cleaning.

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
