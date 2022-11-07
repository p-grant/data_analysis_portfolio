# R Programming
R is a programming language frequently used for statistical analysis, visualization and other data analyses.
## Using and Accessing Files
Use the dir.create function to create a new folder or directory to hold your files.
```R
dir.create(“folder_name”)
```
Use the file.create function to create a blank file. Typically, files will be in the form of a .txt, 	.docx, or .csv file.
file.create(“file_name.type”)
To copy a file, use the file.copy function.
file.copy(“file_name.type”, “destination_folder”).
Delete R files using the unlink function.
unlink(“file_name.type”).
