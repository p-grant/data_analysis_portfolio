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

### Graphical Exploration
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
### Numerical (Statistical) Exploration
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

Tukey's Ladder of Powers: Affecting the values ina dataset will affect the distribution  of the data.

|Power|Example|
|---|---|
|3|$x^3$|
|2|$x^2$|
|1|$x$|
|1/2|$\sqrt{x}$|
|0|$ln(x)$|
|-1/2|$-1/\sqrt{x}$|
|-2|$-1/x$|
|-3|$-1/x^2$|

If we perform one of the example operations shown above, the data will be affected as shown below, where the original distribution is shown at $x$:

![tukeys_ladder_of_powers](https://user-images.githubusercontent.com/114603848/201524421-6c88e259-d857-48e6-a2f8-6dcc3b59b2ec.png)

By performing these operations, we can "undo"  the skewness of the data.

## Descriptive Statistics
We are trying to tell a story with the data, and this is easier if we can use fewer, more descriptive statistics that tell us about our about.

Steps:
- Describe the center of the distribution
  - Mode: The most commonly occuring value in the data.
    - May not be close to the appparent center of the data.
  - Median: The value at the very center of all the datapoints.
    - Hard to use this information.
  - Mean: the average value of the data.
    - $Mean = sum(X)/N$ where X is all of the values in the dataset and N is the number of datapoints
    - Least intuitive of the three. It is the most affected by outliers. However, it is still the most useful, statistically.
- Describe the spread or dispursion of the data
  - Range
    - $Range = Max - Min$
    - Thrown off by outliers.
  - Percentiles and Interquartile Range
    - Interquartile Range (IQR): $IQR = Q3 - Q1$ where Q3 is the third quartile score (75%) and Q1 is the first quartile score (25%).
    - The quartiles are calculated using:
      - $Q1 = 1/4(n+1)^{th}term$
      - $Q2 = 1/2(n+1)^{th}term$
      - $Q3 = 3/4(n+1)^{th}term$
    - Ignores extreme values on either end.
  - Variance and Standard Deviation
    - The variance is the average squared deviation from the mean.
    - $Var = sum(X-M)^2/N$ where M is the mean.
    - The standard deviation is the square root of the variance:
      - $SD = \sqrt{Var}$
    - The formulas are slightly different for populations and samples, but give similar answers if the sample is reasonably large.
    - Least intuitive, affected by outliers, but are also the most useful.
- Describe the shape of the distribution
  - Distribution can:
    - Be Symetrical or Skewed
      - Symetrical: Left and Right sides are (at least close to) identical.
      - Skewed: Most of the scores are on one end.
        - If most of the scores are toward the lower end and there are outliers toward the high end, it is positively skewed.
    - Be Unimodal, Uniform or U Shaped
      - Unimodal: There is only one mode or "hump" in the data.
      - Bimodal: There are two "humps".
      - Uniform: Every value is equally common.
      - U Shaped: Values occur more commonly at the extreme ends of the data.
    - Have Outliers

## Inferential Statistics
Hypothesis Testing allows you to test your theory. Common when a yes/no answer is needed.

Your hypothesis will begin at $H_0$, the Null Hypothesis. This is the hypothesis where there is no systematic effect and random sampling error is the only explanation for any observed differences that are apparent.

The alternative hypothesis, $H_A$, proposes that there is a systematic effect, and that there is a correlation between variables.

We will remove outliers from the greatest and lowest values in our data, using a percent cutoff.

After testing, you will either accept or reject your null hypothesis. It is rejected if there is evidence that the results are not entirely random.

There can be errors: 
- False Positive: Sample shows some effect, but it is truely due to randomness.
  - To have a true false positive, you must first reject your null hypothesis.
  - This is referred to as a Type I Error.
  - You must pick a value to represent the risk of this result (5% is common).
- False Negative: Sample seems to be random, but there is some systematic effect occuring.
  - To have a true false negative, you must first accept your null hypothesis.
  - This is referred to as a Type II Error.
  - This value can be calculated.

Problems with hypothesis testing:
- It is easy to misinterpret.
- We might assume that there is no systematic effect, when there is.
- There might be bias in our cutoff.
- We might not have answered the right question.

Despite these problems, hypothesis testing can still be useful.

Another element of inferential statistics is estimation. This is meant o give you a value to use that describes a parameter.

We can estimate any sample statistic. There are different kinds of estimation:
- Parametric
- Bootstrap Methods

We have certain confidence intervals in our estimations. These can be central or noncentral.

We must first choose aconfidence interval (often 95%).
