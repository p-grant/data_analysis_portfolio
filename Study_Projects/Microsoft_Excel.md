# Microsoft Excel Notes
Importing Data: 
- Select: Data/Get Data/From File/ From Workbook
  - Import the necessary spreadsheet.
- CSV Files: Data/From “Text/CSV” and select the data.
- From Webpages: Data/From Web and enter the URL.

Sorting: Data Menu -> Sort
- Sort Sheet: Sorts all of the data according to how one column is sorted, keeping relevant data together.
- Sort Range: Sorts a single column, without rearranging any other columns.
- SORT(range, column we are sorting by, TRUE/FALSE): 
  - The column we sort by should be denoted by a number (Column B = 2)
  - TRUE: Ascending Order, FALSE: Descending Order

Filtering: Data Menu -> Filter

Edit/Find and Replace to replace certain values in a column with another.

Conditional Formatting: Home Menu -> Conditional Formatting

Remove Duplicates: Data Menu -> Remove Duplicates

Field length is a tool for determining how many characters can be keyed into a field, assigning a certain length to this fields in your spreadsheet is a great way to avoid errors:
- Data -> Data Validation -> Text Length Option

Clear Formatting: Home Menu -> Clear Option (Eraser icon) -> Clear Formatting

The text wrapping feature will set cells to automatically change their height to allow the text in the cell to fit.

Working with text strings: 
- TEXTSPLIT(textstring,”delimiter”): Splits a text string into two columns according to a delimiter.
- CONCAT(text1,text2): Joins two text strings together.
- CONCATENATE(text1,text2,”textstring”,…): Joins multiple text strings into a single string.
- TEXT(cell,”format”): Converts a number into text according to a specified format.
- VALUE(cell): Converts a text string that represents a number to a numerical value.
- LEN(range): Tells you the length of the text string by counting the number of characters it 	contains.
- LEFT(range, number of characters): Gives you a set number of characters from the left side of a 		text string.
- RIGHT(range, number of characters): Gives you a set number of characters from the right side of a 	text string.
- MID(range, reference starting point, number of middle characters): Gives you a segment in the 	middle of a text string.
- TRIM(range): Removes leading, trailing, and repeated spaces in data.
- FIND(character, cell): Used to find the position of a specific character in a text string.
- IFNA(value,value_if_na): Replaces spreadsheet errors with another value.
 - Ex: IFNA(#N/A,’Does Not Exist’).

Formulas all begin with “=”.

Functions:
- Common spreadsheet math functions: SUM, AVERAGE, COUNT, MIN, MAX.
  - SUMIF: (Range, criteria/condition, [Sum Range]):
    - Range = Range we are looking for condition in.
		- Sum Range= Range we are summing over if a certain condition is met.

