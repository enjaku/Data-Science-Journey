Week 2.md
Outliers in Regression     

Types of outliers 
- Outliers that fall horizontally away from the center of the cloud but don't influence the slope of the regression line are called **leverage points**.
- outliers that actually influence the slope of the regression line are called **influential points**.

An influential Point does not neccessarily always reduce R Squared.      

Always view data before deciding what to do.     

Do not throw up the outlier.  Consider cutting the data into two and running regression on both sets.     

Inference with Linear Regression:    
**hypothesis testing**= is the explanatory variable a significant predictor of the response variable? 

![formula](http://latex.codecogs.com/gif.latex?H_0%3A%5Cbeta_1%3D0%3BH_A%3A%5Cbeta_1%20%5Cneq%200 "H\_0:\\beta\_1=0;H\_A:\\beta\_1 \\neq 0")

See written notes:    
T score for all inference    
b1 = point estimate
0 : because in a null hypothesis we always use 0   
SE b1: The standard error for b1
df = n-2:  We loose a df for each parameter that we're estimating.  In this case we are looking at slope and y intercept, hence n-2

![formula](http://latex.codecogs.com/gif.latex?T%20%3D%20%5Cfrac%20%7Bb_1%20-%200%7D%7BSE_b_1%7D "T = \\frac {b\_1 - 0}{SE\_b\_1}")

More notes:    
**Confidence Intervals for the Slope**

![formula](http://latex.codecogs.com/gif.latex?b_1%20%5Cpm%20t_d_f%20%2A%20SE_b_1 "b\_1 \\pm t\_d\_f \* SE\_b\_1")

So this is a ME +- Critical t value x SE    

@ 95% confidence interval..    
1. draw the area under the curve for a two-tailed test     
2. use R qt function to find critical t-value: qt(.972, 25)
    .975 is one side of a 95% confidence interval      
    25 is the degrees of freedom
3.  R gives us -2.06, but take the absolut value = 2.06    

so .9014 (b1, slope estimate from regression output) +- 2.06 * .096 (SE from regression output) = (.7, 1.1)

" We are 95% confident for each additional increase in x, y will increase by 0.7 to 1.1 points"     


**Only use on SAMPLE.  Meaningless if you have POPULATION data.**     
**Biased samples will yield biased results**      
**10% rule that we check if we're sampling without replacement**     


VARIABILITY PARTITIONING:     
AVOVA type output from Regression Output:
   







