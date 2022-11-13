# Math Commonly Use During Analyses
## Algebra
There are three kinds of algebra:
- Elementary
- Linear (Matrix) 
- Systems of Linear Equations
### Elementary Algebra
In elementary algebra, you have one or multiple variables that will affect the equation. An example is shown below:

$$y_i = {B_0+B_1X_{1i}+B_2X_{2i}+B_3X_{3i} \pm E_i}$$

- *E<sub>i</sub>* is the error in our calculation, or how far we expect the calculation to be from the real value.
- Each *B* in this equation is a coefficient of a variable.
- The *i*s in the equation represent which observation we are working with (person, location, product, etc.).
- The *X* values represent each observation's value for that variable (score, price, etc.).

### Linear Algebra
In linear algebra (also known as matrix algebra), there are certain terms we need to know:
- Scalar: One number.
- Vector: One row or column of numbers that can be treated as a collection. Can be thought of as a variable.
- Matrix: Many rows and columns organized in a two-dimensional shape.

Computers are able to work with matrices easily, so linear algebra is important.

An example of a linear algebra equation is shown below:

$$\left\lbrack\matrix{y_1 \cr y_2}\right\rbrack = \left\lbrack\matrix{1 & X_{11} & X_{21} & X_{31} \cr 1 & X_{12} & X_{22} & X_{32}}\right\rbrack\left\lbrack\matrix{B_0 \cr B_1 \cr B_2 \cr B_3}\right\rbrack + \left\lbrack\matrix{E_1 \cr E_2}\right\rbrack$$

In the matrix with the *X*s, the top row contains the variables for observation 1 and the bottom row contains the variables for observation 2.

Here, the *B*s in the vertical vector are the regression coefficients.

To find our *y* values, we first multiply our variable matrix by our regression coefficients:

$$\left\lbrack\matrix{y_1 \cr y_2}\right\rbrack = \left\lbrack\matrix{B_0 & X_{11}*B_1 & X_{21}*B_2 & X_{31}*B_3 \cr B_0 & X_{12}*B_1 & X_{22}*B_2 & X_{32}*B_3}\right\rbrack + \left\lbrack\matrix{E_1 \cr E_2}\right\rbrack$$

$$\left\lbrack\matrix{y_1 \cr y_2}\right\rbrack = \left\lbrack\matrix{B_0 + X_{11}*B_1 + X_{21}*B_2 + X_{31}*B_3 \cr B_0 + X_{12}*B_1 + X_{22}*B_2 + X_{32}*B_3}\right\rbrack + \left\lbrack\matrix{E_1 \cr E_2}\right\rbrack$$

Next, we add the error vector:

$$\left\lbrack\matrix{y_1 \cr y_2}\right\rbrack = \left\lbrack\matrix{B_0 + X_{11}*B_1 + X_{21}*B_2 + X_{31}*B_3 + E_1 \cr B_0 + X_{12}*B_1 + X_{22}*B_2 + X_{32}*B_3 + E_2}\right\rbrack$$

Now, *y*<sub>1</sub> is equal to the top row of the matrix to the right and *y*<sub>2</sub> is equal to the bottom row.

Instead of writing out the entire matrices, we can use matrix notation, where the matrices are denoted by cold characters:

$$Y = XB + E$$

### Systems of Linear Equations
When we have many unknowns and we need to solve for all of them simultaneously, it becomes difficult, especially if the unknown variables depend on each other.

This is where systems of linear equations become handy.

For example, consider this scenario:
- We sold 1000 products
- Some sold for $20 while others sold for $5
- We made $5900
- How many did we sell at each price?

We can create the following equations to represent this situation:
$$Sales: x+y=1000$$
$$Revenue: 20x+5y=5900$$
where x is the number of products sold at $20 and y is the number of products sold at $5.

Next, we can isolate x in the sales equation:
$$x = 1000-y$$

Then, we can substitute x in the revenue equation with this value:
$$20*(1000-y)+5y=5900$$
After simplifying this equation, we find that:
$$y = 940$$
Therefore, we sold 940 units at $5. By plugging this value back into our sales equation for y, we find that:
$$x = 60$$
Therefore, we sold 60 units at $20.

Alternatively, we could isolated y in both equations and plotted both lines. This would have shown us that the lines interest at x = 60, y= 940 (60,940).
## Calculus
Calculus is the basis of many of the procedures in data science, including Least Squares Regression and Probability Distributions.

Calculus is useful for measuring quantities or rates that change over time and for finding the maximum and minimum of functions in optimizing.

There are two kinds of calculus:
- Differential: Rates of change at a specific time. AKA "the calculus of change"
- Integral: Quantity at a specific time given a rate of change. AKA "the calculus of accumulation"

In differential calculus, we can find the derivative, or rate of change (slope of a line) at any point using:
$$f'(x^n) = n{x^{n-1}}$$
## Big Order
## Probability
## Bayes Theorem
