# Week One - Linear Regression and Regression
## Introduction to Linear Regression
### MarkdownPreview - Github
###Insert equation

**Correlation** - the measure of the strength of the linear relationship between two numerical variables.

y- axis: Response Variable    
x- axis: Explanatory Variable     

* Relationship:
    + Form (Linear or NonLinear)
    + Direction (Negative or Positive) 
    + Strength (**Correlation denoted with R**)
       
        ![formula](http://latex.codecogs.com/gif.latex?R%20%5Csimeq "R \\simeq")

* Properties of the Correlation Coefficient:
    + Magnitude (absolute value)
    + The higher the 0.num the stronger the correlation
        + The higher the "scatter" the weaker the strength or Correlation Coefficient (R)
    + The sign of the Correlation Coefficient indicates the **direction of the association**.
    + Correlation Coefficient is always between -1 (perfect neg correlation) and +1 (perfect pos correlation)
    + 0 indicates NO Correlation
    + Unitless - Not effected by change in units
    + ** The Correlation of X with Y is the same as Y with X**  You can swap the axis.
    + Sensitive to Outliers

**Residuals** - Leftovers from the model fit - "The difference between the observed and the predicted Y.

![formula](http://latex.codecogs.com/gif.latex?%24%20e_i%20%3D%20y_i%20-%20%5Chat%7By_i%7D "$ e\_i = y\_i - \\hat{y\_i}")

**e = Observed - Predicted**

**Least Squares**
   * Most commonly used
   * Easier to compute
   * A residual twice a large is another is more than twice as bad

![formula](http://latex.codecogs.com/gif.latex?%5Chat%7By%7D%20%3D%5Cbeta_0%20%2B%20%5Cbeta_1%20x "\\hat{y} =\\beta\_0 + \\beta\_1 x")

x = explanatory variable
B1 = slope
B0 = y intercept
y(hat) = predicted response

b1 = point estimate of intercept
b1 = point estimate of slope

![formula](http://latex.codecogs.com/gif.latex?slope%20%3D%20b_1%20%3D%20%5Cfrac%20%7Bs_y%7D%7Bs_x%7D%20R "slope = b\_1 = \\frac {s\_y}{s\_x} R")

This is a rise over run equation
sx: SD of x
sy: is SD of y
R = cor(x,y)

The interpretation of the slope is about the relationship bwtween the explanatory and response variables.  How do we expect the response varaiable to change as we increase the explanatory variable by one unit?

**Avoid Causal Language**

**Intercept**
The line will always go through x(bar), y(bar), e.g. the line will always go through the mean of x and the mean of y.

So plug in x(bar) and y(bar) into the equation, rearrange,  and you get:

![formula](http://latex.codecogs.com/gif.latex?b_o%20%3D%20%20%5Cbar%20%7By%7D%20%3D%20b_1%20%5Cbar%7Bx%7D "b\_o =  \\bar {y} = b\_1 \\bar{x}")

**For each increas in x:  y is expected to be higher or lower by the value of the slope.**
































