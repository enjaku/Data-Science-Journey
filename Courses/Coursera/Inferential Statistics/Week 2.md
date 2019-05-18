#Week 2#

**Null Hypothesis** ![formula](http://latex.codecogs.com/gif.latex?H_%7B0%7D "H\_{0}") that observations are due to chance, the status quo.
    - Set to = some parameter.   Always ![formula](http://latex.codecogs.com/gif.latex?%5Cmu%20NOT%20%5Cbar%7Bx%7D "\\mu NOT \\bar{x}")
**Alternative Hypothesis** ![formula](http://latex.codecogs.com/gif.latex?H_%7BA%7D "H\_{A}") The research question.  What we're testing for.
    - set to !=, < or > the parameter.

Hypothesis are aways about the **population parameters** and not about the sample statistics.  So common hypothesis notaion is: ![formula](http://latex.codecogs.com/gif.latex?%5Cmu "\\mu") or ![formula](http://latex.codecogs.com/gif.latex?%5Csigma "\\sigma").

**p-value:**    
The probabliity (P) of more exreame outcomes given that ![formula](http://latex.codecogs.com/gif.latex?H_%7B0%7D "H\_{0}") is true.

**Standard Error(SE):**  
Is the standard deviation of the samplying distributions of the mean. 
![formula](http://latex.codecogs.com/gif.latex?SE%20%3D%20%5Cfrac%7Bs%7D%20%7B%5Csqrt%7Bn%7D%7D "SE = \\frac{s} {\\sqrt{n}}")   




**Z score**   
"The number of standard deviations an observation falls above or below the mean"

Calculated as: "observed sample mean "![formula](http://latex.codecogs.com/gif.latex?%5Cbar%7Bx%7D "\\bar{x}")" **minus** the Null Hypothesis ![formula](http://latex.codecogs.com/gif.latex?H_%7B0%7D "H\_{0}") all over the SE.
    
![formula](http://latex.codecogs.com/gif.latex?z-score%20%3D%20%5Cfrac%7B%5Cbar%7Bx%7D%20-%20%7BH_0%7D%7D%20%7BSE%7D "z-score = \\frac{\\bar{x} - {H\_0}} {SE}")
 
 This yields a **"Test Statistic"** that will be used to find the p-value.

 Z-scores gives you the area to the left of the score, e.g. the percentage of points that call BELOW a given observation.

*Video is Intro to Statistics, Week 4, Normal Distribution (17 mins) 10:06*

Alright sports fans, here's how to use pnorm.  It takes 3 arguments:   
1. The observation on intrest.  The point on the curve that you're interested in.   
2. the mean of the sample distribution or the population   
3. the standard deviation or SE in the case of sample distributions

pnorm will give the probabliity of everything to the **LEFT** of the observation of intrest, so you may have to subtract from 1.  

**Level of Significance aka ![formula](http://latex.codecogs.com/gif.latex?%5Calpha "\\alpha") is normally set at .01, .05 or 1.0.
**"If the P-value is low, the Null must go"** - If the p-value is lower than the set alpha, then we reject the Null Hypothesis.  Or, **"If the P is high, the Null must fly".**

###Two-Sided Tests###
To find the cut-off values take the z-score in the opposite direction of the mean.  So if the z-score is 1.5 from a mean of 0, the other tail is -1.5.
![formula](http://latex.codecogs.com/gif.latex?P%28%5Cbar%7Bx%7D%29%3E1.5%20OR%20%3C1.5%20%7C%20H%5C_0%20%3A%20%5Cmu%20%3D%200 "P(\\bar{x})>1.5 OR <1.5 | H\\\_0 : \\mu = 0")

The P-value on the lower tail is the same as the upper tail.  Make sure that you draw this out to make sense of it.

###Hypothesis Testing for a Single Mean###

1.  Set Hypothesis ![formula](http://latex.codecogs.com/gif.latex?H_0 "H\_0") and ![formula](http://latex.codecogs.com/gif.latex?H_A "H\_A")
2.  Calculate the Point Estimate ![formula](http://latex.codecogs.com/gif.latex?%5Cbar%7Bx%7D "\\bar{x}")
3.  Check conditions:
     - Independence: Sampled observations must be independent (random sample/assignment, and if sampling without replacement, n < 10% of the population).
     - Sample Size/Skew:  n >= 30, larger if the population is very skewed.
4. Draw the samplying distribution, shade the p-value, and calculate the test statistic (Z-score ... see formuulas above).
5. Make a decision and interpret in context of research question.
     - "If the P-value is low, the Null must go"
     -  "If the P is high, the Null must fly"



