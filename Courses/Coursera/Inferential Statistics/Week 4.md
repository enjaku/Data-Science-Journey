#Week 4

Inference for categorical variables (binary), where the parameter of interest is a proportion, as opposed to the mean. 

The **Parameter of Interest** is the Proportion of Success.  
For categorical variables the parameter of interest is **proportion**.  

Categorical Variables take on names, like the color of cars (red, green, black).  Factors.

So we sample the population (Smoke or No Smoke) and come up with proportions  ![formula](http://latex.codecogs.com/gif.latex?%5Chat%7Bp%7D "\\hat{p}") for each country.  Combinded we have a **Sampling Distribution of Proportaions**.

So we start with a categorical variable (Smoke, No Smoke), and now have a proportion, which is a **Numerical variable**, e.g. the % of Smokers. 

**CLT for Proportions** 

![formula](http://latex.codecogs.com/gif.latex?%5Chat%7Bp%7D%20%5Csim%20N%20%28mean%20%3D%20p%2C%20SE%20%3D%5Csqrt%20%5Cfrac%7Bp%281-n%29%7D%7Bn%7D%29 "\\hat{p} \\sim N (mean = p, SE =\\sqrt \\frac{p(1-n)}{n})")

- The distribution of sample proportions is going to be nearly normal 
- Centered at the population proportion suppose this population mean
- Generically, it's centered at the population parameter
- Standard error inversely proportional to sample size 

CLT tells us about:
- The shape of the distribution (p~N)
- The center of the distribution (mean = p)
- spread of the distribution (sqrt of...)

![formula](http://latex.codecogs.com/gif.latex?SE%20%3D%20%5Csqrt%20%5Cfrac%20%7Bp%281-n%29%7D%7Bn%7D "SE = \\sqrt \\frac {p(1-n)}{n}")

Conditions:
- Sampled observations must be independent
    + random sample/assignment
    + if sampling without replacement the sample size < 10% of P(opulation)
-  Sample Size there should be atleast 10 Successes and 10 Failures in the sample.
- p is unknown, use p(hat) the sample statistic.

EXAMPLE: 
We're told that **90%** of all plant species are classified as angiosperms, so our **proportion of success is 0.9 or 90%**. We're also told that our **sample size is 200, so n is 200**. And we're asked for the **probability of at least 95% successes**.

-  p=0.90    
-  n = 200    
-  p(p-hat) > 0.95  (The Probability that the sample proportion will be greatere than .95)   

1.  Do conditions hold?
2.  Make sure that you have 10 success and failures in the sample.

![formula](http://latex.codecogs.com/gif.latex?%5Chat%7Bp%7D%5Csim%20N%28mean%20%3D%200.90%2C%20SE%3D%5Csqrt%20%5Cfrac%7B0.90%20x%200.10%7D%7B200%7D "\\hat{p}\\sim N(mean = 0.90, SE=\\sqrt \\frac{0.90 x 0.10}{200}")

= 0.0212   

3.  Draw curve.  Shade above .95 since we're looking for "at least 95%...
4.  Now calc the Z score:
![formula](http://latex.codecogs.com/gif.latex?Z%20%3D%20%5Cfrac%7B0.95%20-%200.90%7D%7B0.0212%7D "Z = \\frac{0.95 - 0.90}{0.0212}")

    Z = (Observed - Null)/SE  

5.  Z Score = 2.36 

6.  Plug into pnorm and get roughly 0.009.
    1- pnorm(2.36, 0, 1)
      **Remember in a Z score the Mean is always 0 and the SD is 1**

      Could have done this with a Binomial Distribution as well
      200 x .95 = 190
      R:  > sum(dbinom(190:200, 200, 0.90))
      **REVIEW BINOMIAL DISTRIBUTIONS**
 
 ##Confidence Interval for a Proportion  

   point estimate (p(hat)) +- margin of error    


  ![formula](http://latex.codecogs.com/gif.latex?%5Chat%7Bp%7D%20%5Cpm%20z%5E%2A%20%7BSE_%5Chat%7Bp%7D%7D "\\hat{p} \\pm z^\* {SE\_\\hat{p}}")  

  How to calculate the SE for a proportion, for calulating a confidence interval.

  ![formula](http://latex.codecogs.com/gif.latex?SE%20%5Chat%7Bp%7D%3D%5Csqrt%20%5Cfrac%7B%5Chat%7Bp%7D%281-%5Chat%7Bp%7D%29%7D%7Bn%7D "SE \\hat{p}=\\sqrt \\frac{\\hat{p}(1-\\hat{p})}{n}")

  If we do not know the True Population Proportion (P) we use the Sample Proportion (P(hat)).


##Example:
  **Going back to the data that we had, the general social survey found that 571 out of 670, that's roughly 85% of Americans, answered the question on experiment design correctly. We are asked to estimate using a 95% confidence interval, the proportion of all Americans who have good intuition about experiment design.**

  p(hat) = .85
  CI of 95% is = z* of 1.96 (we know this)
  n = 670  


1.  Are the conditions met for inference?
    a. independence must be less than 10% of the population (670 < American population).

    b.  Success/Failure Condition:  At least 10 of each in the sample.
    since the success-failure condition is met we can assume that the sampling distribution of the proportion is nearly normal. 

2. Calculate the Confidence Interval:   

   ![formula](http://latex.codecogs.com/gif.latex?%5Chat%7Bp%7D%20%5Cpm%20z%5E%2A%20%7BSE_%5Chat%7Bp%7D%7D "\\hat{p} \\pm z^\* {SE\_\\hat{p}}")  

  .85 +- 1.96 (95% CI) Sqrt (.85 x .15)/670  

  SE = .0138 so...

  (1.96 x .0188) is known as the "MARGIN OF ERROR" Who'd a think it?

 = .85 +- 1.96 x .0138
 = .85 +- 0.027  
 or 
 (0.823, 0.877)
 
 We are 95% confident that 82.3% to 87.7% of Americans have good intuition about experimental design.

 The **confidence level** is about percentage of samples that yield intervals capturing the population parameter.   


**Key Point**  The **Margin of Error** tells you how many percentage points your results will differ from the true population mean.  For example, a 95% **Confidence Interval** with a 4% **Margin of Error** means that your statistic will be within 4 percentage points of the true population value 95% of the time.

**If, for a new confidence interval based on a new sample, we wanted to reduce the margin of error to 1% while keeping the confidence level the same. At least how many respondents should we sample?**

We'll use the same p(hat) (.85) because we already know it from previous.

ME = 0.01 = 1.96 x Sqrt(.85 x .15)/ n 

Sovle for n  
    Square both sides and shuffle things around 
     n = 4898.04  ROUND UP!!  to 4,899 people.

** For minor reduction is **Margin of Error** need a major increase in **Sample Size**.

One final thought on calculating sample size to desired Margin of Error:
    It's a critical value times the standard error. If there is a previous study that we can rely on for the value of p-hat in this formula, we would use that in calculation of the required sample size.
    **If not, then we're going to use 0.5 for our p-hat**. _We'll see this again_  Yup, it JUST did!!

    























 