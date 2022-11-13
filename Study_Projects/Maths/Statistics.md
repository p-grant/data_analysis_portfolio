# Statistics
Statistics is useful because counting is easy, but summarizing and generalizing are hard.

There are different methods in statistics:
- Descriptive
- Inferential
- Hypothesis Testing
- Estimation

There are different choices that must be made:
- Estimators
- Measures of Fit
- Feature Selection
- Common Problems
- Model Validation

## Exploring Data
We want to see what our dataset is like and if our assumptions are met. We want to listen to the data.

There  are two kinds of exploration:
- Graphical
  - Use graphs to explore data visually.
  - Graphics are dense in information.
  - Best for overall impression.
- Numerical
  - Gives greater precision. 
  - Try variations of data and methods.
  - Second step.

## Graphical Exploration
Gives you a "feel" of the data. Allows you to check assumptions and anomolies, and to get suggestions for your analysis.

This exploration should be performed first, because:
- Graphics are information dense
- Humans are visual
- Graphics are the best way to check shape, gap and outliers

Questions you are trying to answer:
- Do you have what you need?
- Are there clumps or gaps in the data?
- Are there exceptional cases and/or outliers?
- Are there errors in the data?

There are several ways to perform this exploration:
- Code
  - R/Python
  - JavaScript
- Apps
  - Tableau
  - Qlik
  - Excel
- By Hand

Plots for analyzing one variable (univariate distributions):
- Bar Charts
  - Used when dealing with categories
  - Easy to read
  - Several format options
    - Descending/Ascending
    - Horizontal/Vertical
- Histograms
  - Used for quantitative variables
  - Shows you the shape of a distribution
  - Allows you to compare many variables
- Boxplot
  - Used for quantitative variables and when you have many variables
  - Shows quartile values and outliers

Plots for analyzing two variables (bivariate distributions):
- Groups of univariate plots
  - Good for seeing the association of categories and the outcome
- Scatterplot
  - Two quantitative variables
  - Allows you to check for linearity, outliers, and the strength of association

Plots for analyzing multiple variables (multivariate distributions):
- Avoid using 3-dimensional plots, as they can be difficult to interpret
  - If you do use 3D graphics, they must be in motion
  - Might be useful for clustering in some circumstances, however
- Matrices of plots
  - Many quantitative variables
  - Can use markers for groups
  - Clearer than 3D
## Numerical (Statistical) Exploration
Performed after the graphical method of exploration.

Used to transform and manipulate the data, take empirical estimates, use more robust methods, and check the sensitivity of the results.

You are still exploring the data, you are not yet creating models.

Robust statisitcs are stable estimates. They are less affected by outliers, skewness, jurtosis,etc.

Trimmed Mean: Remove a certain percentage of the data away from the greatest and least outlying data. Calculate the mean of the remaining data.

Winsorized Mean: Move the most outlying data points to values closer to the general collection of data points, and then calculate the mean.

For example, we can calculate the trimmed and winsorized means for the boxplot shown below:

![boxplot_for_means](https://user-images.githubusercontent.com/114603848/201523495-2d1f5bff-3c05-4dec-86d7-294471b076e6.png)

The values calculated for both kinds of mean are shown below:

|Data Changed/Removed|Trimmed Mean|Winsorized Mean|
|---|---|---|
|0%|1.24|1.24|
|5%|1.14|1.19|
|10%|1.10|1.16|
|25%|1.03|1.07|
|50%|1.01|1.01|

When we change or remove 50% of the greatest and least outying data, the only value remaining is the median.

Resampling is the act of performing the same analysis on different sample groups of the same population. It gives an empirical estimate of sampling variability. Important to the process of cross-validation.

There are several versions of resampling:
- Jackknife
- Bootstrap
- Permutation

Transforming dataset involves using "smooth" functions on complicated data. It preserves the order of the data and allows you to work on the full dataset. You can fix skewed data and curved lines using this method.

Tukey's Ladder of Powers:

|3|$x^3$|
|2|$x^2$|
|1|$x$|
|1/2|$\sqrt{x}$|
|0|$ln(x)$|
|-1/2|$-1/\sqrt{x}$|
|-2|$-1/x$|
|-3|$-1/x^2$|
