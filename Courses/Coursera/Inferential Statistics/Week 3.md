#Week 3
##Inferential Statistics

###Inference for Numerical Variables  

T-distribution is useful in describing the sample mean when the population standard deviation ![formula](http://latex.codecogs.com/gif.latex?%5Csigma "\\sigma") is unknown.   

Why large sample sizes?
    - the sampling distribution of the mean is nearly normal
    - the estimate of the Standard Error is reliable:  ![formula](http://latex.codecogs.com/gif.latex?%5Cfrac%7Bs%7D%20%7B%5Csqrt%20%7Bn%7D%7D "\\frac{s} {\\sqrt {n}}")

When ![formula](http://latex.codecogs.com/gif.latex?%5Csigma "\\sigma") is unknown almost always use the t-distribution.
    - squished in the middle
    - thicker tails
    - confidence intervals are wider
    - z-scores of 2 are not uncommon
    - one parameter: **Degrees of Freedom** , not two (mean and sd)
    - as the degrees of freedom increases the shape of the t distribution approaches the normal distribution

T statistic is calculated just like a Z statistic.  

![formula](http://latex.codecogs.com/gif.latex?T%20%3D%20%5Cfrac%7BObserved%20-%20Null%7D%7BSE%7D "T = \\frac{Observed - Null}{SE}")
    - find p-value the probability of observed or more extreme outcome given that the null hypothesis is true.   

The probablity that the absolute value of Z is greater than 2:   
    pnorn(2, lower.tail = FALSE) * 2

The probability that the absolute value of t with 50 degrees of freedom is greater than 2:   
    **pt** (2, df = 50, lower.tail = false) * 2  
        - pt(q, df, ncp, lower.tail = TRUE, log.p = FALSE)
 
 Going from t distribution with a high degrees of freedom to a t distribution with low degrees of freedom, the probability of the test statistic being more than two standard deviations away from the mean *Increases* . 

 Dreg Freedom ![formula](http://latex.codecogs.com/gif.latex?%5Cdownarrow "\\downarrow")  Probability ![formula](http://latex.codecogs.com/gif.latex?%5Cuparrow "\\uparrow")

 As we get more conservative with **lower degrees of freedom** we are less likely to reject the Null Hypothosis.

##Inference for the Mean

 point estimate +- Margin of Error    
 ![formula](http://latex.codecogs.com/gif.latex?%5Cbar%7Bx%7D%20%5Cpm%20%7B%7Bt%5E%2A%7D_d_f%7D%20%7BSE_%5Cbar%7Bx%7D%7D "\\bar{x} \\pm {{t^\*}\_d\_f} {SE\_\\bar{x}}")

 ![formula](http://latex.codecogs.com/gif.latex?SE%20%3D%20%5Cfrac%20%7Bs%7D%20%7B%5Csqrt%7Bn%7D%7D "SE = \\frac {s} {\\sqrt{n}}")

 So the only new item is figuring out the critical t-score.  How do we fine that?   
    1.  find the degrees of freedom    df = (n-1)   
    2.  find corresponding tail area for the desired confidence intervals   
    3. qt(0.025, df = 21)  - from example of 95% (.950) confidence level.  two tails, so .025 at each tail.

Conditions for t-statistic:
    1. independance      
    2. < 10% of n         
    3. skewness is ok, so long as its not too extreame

##Inference for Comparing Two Independent Means
###Estimating the difference between two means

![formula](http://latex.codecogs.com/gif.latex?%28%5Cbar%7B%7Bx%7D_1%7D%20-%20%5Cbar%7B%7Bx%7D_2%7D%29%20%5Cpm%20%7B%7Bt%5E%2A%7D_d_f%7D%20%7BSE_%28%5Cbar%7B%7Bx%7D_1%7D%20-%20%5Cbar%7B%7Bx%7D_2%7D%29 "(\\bar{{x}\_1} - \\bar{{x}\_2}) \\pm {{t^\*}\_d\_f} {SE\_(\\bar{{x}\_1} - \\bar{{x}\_2})")

The SE is a nightmare:
![formula](http://latex.codecogs.com/gif.latex?%5Csqrt%7B%5Cfrac%7Bs_1%5E2%7D%7Bn_1%7D%2B%5Cfrac%7Bs_2%5E2%7D%7Bn_2%7D%7D "\\sqrt{\\frac{s\_1^2}{n\_1}+\\frac{s\_2^2}{n\_2}}")    

df = smallest n - 1

Conditions:
Independence both within the groups and from each other   

The more skewed the populations, the larger the sample that we need   

##Example

**5:05 Video Point**

See notebook for example...

We got the T statistic from:
![formula](http://latex.codecogs.com/gif.latex?T%20%3D%20%5Cfrac%7BObserved%20-%20Null%7D%7BSE%7D "T = \\frac{Observed - Null}{SE}")

SE is calculated:

![formula](http://latex.codecogs.com/gif.latex?%5Csqrt%7B%5Cfrac%7Bs_1%5E2%7D%7Bn_1%7D%2B%5Cfrac%7Bs_2%5E2%7D%7Bn_2%7D%7D "\\sqrt{\\frac{s\_1^2}{n\_1}+\\frac{s\_2^2}{n\_2}}") 

That's read (s^2 of 1 over n of 1) **plus** (S^2 of 2 over n or 2)
It's not some fucking, goofy notaion!!

One thing... p-values are hard to find.   
We have a T-statistic of 2.24.  We know that the df is 21 (smallest n - 1).   
This is a two-tailed test since the H0 is = 

The R code is: (1 - **pt**(2.24, df = 21)) * 2

This yields a P of .04.  We have a 95% confidence interval, so "If the P is low, the Null must go"... We reject the Null Hypothosis.











