#Week 2#

**Null Hypothesis** ![formula](http://latex.codecogs.com/gif.latex?H_%7B0%7D "H\_{0}") that observations are due to chance, the status quo.
    - Set to = spme parameter
**Alternative Hypothesis** ![formula](http://latex.codecogs.com/gif.latex?H_%7BA%7D "H\_{A}") The research question.  What we're testing for.
    - set to !=, < or > the parameter

Hypothesis are aways about the **population parameters** and not about the sample statistics.  So common hypothesis notaion is: ![formula](http://latex.codecogs.com/gif.latex?%5Cmu "\\mu") or ![formula](http://latex.codecogs.com/gif.latex?%5Csigma "\\sigma").

**p-value:**    

The probabliity (P) of more exreame outcomes given that ![formula](http://latex.codecogs.com/gif.latex?H_%7B0%7D "H\_{0}") is true.

**Standard Error(SE):**    

Is the standard deviation of the samplying distributions of the mean. 
![formula](http://latex.codecogs.com/gif.latex?SE%20%3D%20%5Cfrac%7Bs%7D%20%7B%5Csqrt%7Bn%7D%7D "SE = \\frac{s} {\\sqrt{n}}")       


**Z score**   

**"The number of standard deviations an observation falls above or below the mean"**

Calculated as: "observed sample mean "![formula](http://latex.codecogs.com/gif.latex?%5Cbar%7Bx%7D "\\bar{x}")" **minus** the Null Hypothesis ![formula](http://latex.codecogs.com/gif.latex?H_%7B0%7D "H\_{0}") all over the SE.
    
![formula](http://latex.codecogs.com/gif.latex?z-score%20%3D%20%5Cfrac%7B%5Cbar%7Bx%7D%20-%20%7BH_0%7D%7D%20%7BSE%7D "z-score = \\frac{\\bar{x} - {H\_0}} {SE}")
 
 This yields a **"Test Statistic"** that will be used to find the p-value.

 Z-scores gives you the area to the left of the score, e.g. the percentage of points that call BELOW a given observation.

*Video is Intro to Statistics, Week 4, Normal Distribution (17 mins) 10:06*

Alright sports fans, here's how to use pnorm.  It takes 3 arguments>
1. The observation on intrest.  The point on the curve that you're interested in.
2. the mean of the sample distribution or the population
3. the standard deviation or SE in the case of sample distributions

pnorm will give the probabliity of everything to the **LEFT** of the observation of intrest, so you may have to subtract from 1.  



