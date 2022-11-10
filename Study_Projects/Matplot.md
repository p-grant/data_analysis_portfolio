# Python's Matplot Package
The Matplot package is a popular data visualization package.

The most popular module is pyplot. 

Import pyplot using:
```Python
import matplotlib.pyplot as plt
```
## Scatterplots
To create a line plot of two arrays, use the plot method:
```Python
plt.plot(x_array,y_array)
```
To create a scatter plot of two arrays, use the scatter method:
```Python
plt.scatter(x,y)
```
To define the color of the circles, use:
```Python
.scatter(x, y, c=list_of_values)
```
The colors will range according to the scale of the list given.

To define the size of the circles, use:
```Python
.scatter(x, y, s=numerical_list_of_circle_areas)
```
The area of each circle is determined by the numbers in our list.

To change the colormap, use:
```Python
.scatter(x,y,cmap=”cmap_name”)
```
Many colormap options exist, including: Spectral, jet_r, plasma_r, viridis,	viridis_r, and many more.

To include a color bar next to the graph, use:
```Python
plt.scatter(x,y,…)
plt.colorbar()
```
## Other Plots
Create a histogram using:
```Python
plt.hist(list_of_values, bins=number_of_bars, histtype=’bar’, color=’desired_bar_color’, edgecolor=’desired_bar_edge_color’)
```
Create a bar plot using:
```Python
plt.bar(x, y, width= bar_width_in_inches, color = ‘bar_color’)
```
Create stacked bar graphs by plotting one bar plot on top of another.

Create a boxplot using:
```Python
plt.boxplot(values)
```
## More Plot Options
To limit the borders of a plot, use:
```Python
plt.xlim(xmin=minimum_value, xmax=maximum_value)
plt.ylim(…)
```
Use the label property to label a line in a plot:
```Python
plt.plot(x,y,label=”label”)
```
To change the color of our data points, use the color property:
```Python
plt.plot(x,y,color = ’color’)
```
To change the line type of a line, use:
```Python
plt.plot(x,y,’-green’)
```
for a solid green line,
```Python
plt.plot(x,y,’--green’)
```
for a dashed green line,
```Python
plt.plot(x,y,’-.green’)
```
for a dashdot green line, and
```Python
plt.plot(x,y,’:green’)
```
for a dotted green line.

To plot two lines on the same plot, simply follow one plot method by another:
```Python
plt.plot(x,y,color=’green’)
plt.plot(x,y-1,color=’red’)
```
Both lines will be shown on the same plot.

To add a title to a plot, use the title method:
```Python
plt.title(“plot title”)
```
To add axis labels to a plot, use the xlabel and ylabel methods:
```Python
plt.xlabel(“x label”)	
```
To include a legend showing the labels for each line on a figure, use the legend method:
```Python
plt.legend()
```
To show a plot, use the show method:
```Python
plt.show()
```
## Figures
To create a figure, use the figure method:
```Python
plt.figure(figsize=(width_in_inches,height_in_inches))
```
To display multiple plots on the same figure, use the subplot method:
```Python
plt.subplot(number_of_rows,number_of_columns,plot_position)
```
The figure will contain a specific number of rows and columns where plots will	be shown.

To save a figure, use:
```Python
plt.savefig(‘figure_name.png’)
```
