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

##Hypothessis Testing of a Proportion:

From a YouTube Video -
1. State the Null Hypothessis.  Alt Hypothessis can be !=, < or >.    
2.  Calculate point estimate p(hat)
3.  Check conditions: independence (< 10% of population **without replacement**
    np>=10 AND n(1-p)>=10   **Note: p NOT p(hat)**
Choose the Level of Significance:  Normally between 0.05 and 0.01.  
4.  Draw samplying distribution and draw curve.   
3. Find critical values: A Z value or a T value that seperate the taisl(s) from the rest of the curve.  How do you know???
    -With proportions we use a **Z Value** for large enoght sample size.
    - p(portion of the population) x n (sample size) > 5  also (1-p)n >5.  
4. Find the test statistic:  Z = (p(hat) - p) / SE where:
                SE sqrt {p(1-p) \ n}

5. Find p-value < Significance Level (alpha) reject the Null.  If thep is low, the Null must Go.


When you use p(h) v. p:

Success-Failure      
        -Confidence interval:  p(h)     
        -Hypothessis test: p    

Standard Error:    
        -Confidence interval:  p(h)     
        - Hypothessis testing: p     

##Exercise:

 Pew Research poll found that 60% of 1,983 randomly sampled American adults believe in evolution. Does this provide convincing evidence that majority of Americans believe in evolution? And when say majority, what we mean is more than 50%.

H0: p = .50 of americans believe in evelution
HA: p > .50 of americans...

Sample Proportion (p{h}) is 0.6    
n = 1,983   

conditions:  independence: gtg, skew: success and failures > 10: gtg

**Since Success condition is met:  Assume nearly normal distribution.** 

p{h} ~N (mean = 0.5)  SE = sqrt{(05 -05)} 1,983

SE = .0112

Calculate the test statistic (Z)   (.6 - .5) / .0112 (SE)

Z = 8.982  
p = the area under the cruve beyond 8.92 is going to be almost 0


##Estimating the Difference Between Two Proportions:

calculating a confidence interval for the difference between the two population proportions ,that are unknown using data from our sample.    

EXAMPLE:
Parameter of interest is the difference between all Coursera students and all Americanswho believe there should be a ban on handguns:

Parameter of Interest: Pcoursera - Pus  with P being Population Proportion   
Sample Statistic (Point Estimate): p(hat)corsera - p(hat)us  

Estmations are Confidence Intervals, and CIs are always:

point estimate +- margin of error

close enough:

![formula](http://latex.codecogs.com/gif.latex?%28%5Chat%7Bp_1%7D%20-%20%5Chat%7Bp-2%7D%20%5Cpm%20z%5E%2A%20%7BSE_%7B%28/hat%7Bp_1%7D-/%7Bhat%7Bp_2%7D%29%7D "(\\hat{p\_1} - \\hat{p-2} \\pm z^\* {SE\_{(/hat{p\_1}-/{hat{p\_2})}")

Standard Error    

![formula](http://latex.codecogs.com/gif.latex?SE%20%3D%20%5Csqrt%5Cfrac%20%7Bp_1%20%281%20-%5Chat%7Bp_1%7D%29%7D%7Bn_1%7D%20%2B%20%5Cfrac%20%7Bp_2%20%281%20-%5Chat%7Bp_2%7D%29%7D%7Bn_2%7D "SE = \\sqrt\\frac {p\_1 (1 -\\hat{p\_1})}{n\_1} + \\frac {p\_2 (1 -\\hat{p\_2})}{n\_2}")


we're adding the two Variability components here, and then **taking the square root of that, to go from variance, to standard deviation** or in other words, the standard error, which is basically the standard deviation of the sampling distribution.

Conditions:    
-withing groups independence    
    random sampling/assignment    
    if samplying **without replacement**, n<10% of population   
-between groups: independent 

Sample Size to **Ensure Normality** of sample:
- each sample should meet success-failure conditions:
    + n:p >= 10 and n(1-p) >= 10  **Both Samples**    

The rest is pretty straight forward.  Z^* is going to be a Z score of 95% CI.
If you have **successes** subtract from sample population to get **failures**

Running the math:     
Point Estimate += Margin of Error x SE         
(0.71 - 0.25) +- 1.96 x 0.0516       
0.46     +-  0.10       
Therefore the **Overall Confidence Interval** is(0.36 , 0.56 )

What this means is that we are 95% confident ,that the proportion of Coursera students who believe that their should be a ban on possession of handguns ,is 36 to 56% higher than the proportion of Americans who do.

Does the order of observations matter?  No.    

##Hypothessis Test for Comparing Two Proportaions  

To calculate p(hat) = divide value of interest by total population.   

**For One Propotion**   
Confidence intervals: p(hat)     
For hypothesis tests: P   

**For Two Proportions:**
Convidence Intervals use p(hat)   

 **Pooled Value**  In a hypothesis test, we must assume that the null hypothesis is true. And when we're doing a hypothesis test for comparing two proportions. Our null hypothesis states that the two proportions are equal to each other, so we're going to use this value of the pooled proportion to say this is the value they're equal to.


For hypothesis testing: **Pooled Proportion**  
    ![formula](http://latex.codecogs.com/gif.latex?Pooled%20Proportions%20%3D%20%5Chat%7BP%7D%20%3D%20%5Cfrac%7Btotal%20successes%20in%20both%20groups%7D%7Btotal%20n%20from%20both%20groups%7D "Pooled Proportions = \\hat{P} = \\frac{total successes in both groups}{total n from both groups}")

  Success-Failure:    
    n1P(ool) >= 10   
    n1(1-P(ool)) >=10   

n2P(ool) >=10   
n2(1-P(ool)) >=10   

**Continuity Notes:  I'm going sailing.  We left off at calculating the Standard Error using a _pooled value_ for P(hat)  We just need to know the formula for calculating the SE with the pooled value, aka P(hat)**

Success-Failure for hypothesis test:

![formula](http://latex.codecogs.com/gif.latex?%7Bn_1%7D%5Chat%7B%7BP%7D_p_o_o_l%20%7D%5Cgeq%2010 "{n\_1}\\hat{{P}\_p\_o\_o\_l }\\geq 10")

![formula](http://latex.codecogs.com/gif.latex?%7Bn_1%7D%281-%5Chat%7B%7BP%7D_p_o_o_l%20%7D%29%5Cgeq%2010 "{n\_1}(1-\\hat{{P}\_p\_o\_o\_l })\\geq 10")

...and the same for n2..

To calculate the standard error we plug in P(ooled) everyplace that we see a p(hat)1 or a p(hat)2  .

![formula](http://latex.codecogs.com/gif.latex?SE%20%3D%20%5Csqrt%5Cfrac%20%7Bp_1%20%281%20-%5Chat%7Bp_1%7D%29%7D%7Bn_1%7D%20%2B%20%5Cfrac%20%7Bp_2%20%281%20-%5Chat%7Bp_2%7D%29%7D%7Bn_2%7D "SE = \\sqrt\\frac {p\_1 (1 -\\hat{p\_1})}{n\_1} + \\frac {p\_2 (1 -\\hat{p\_2})}{n\_2}")

**12:28 in the HowTest for Comparing Two Proportions**

We're looking at a two-tailed test at 0.12 at each end.   
Calculate the Z-Score = (-0.12 - 0)/0.0619 (SE)     

Z= -1.74  

P=value the probablity of being below the Z of 01.74 AND abpve 1.74.     
 = 0.08%

 Significance level is 95%, so 0.08 is NOT LESS than 0.05, so we cannot reject the NUll that the proportions are the same.   

 ##Small Sample Proportions

 What if the S-F is NOT met?

 Ho: p= 0.5    
 Ha = p > 0.5   

 n=8   
 p(hat) = 1 (the outcome of guessing all 8 coin flips correctly)

 Conditions for Inference:
 Independence:  Givien a fair coin we can assume independence.    
 Sample Size/Skew:  8 trials x 0.5 (Null value) = 4 **Not Met**    

 The result is that we cannot assume the distribition is nearly normal, and we cannot use methods that rely on the CLT.    

 **Enter "Simulation Based Inference"**     

 1.  Ultimate goal is to get a p-value.
 2.  P(observed or more extreame outcome \Ho is TRUE)
 3.  Devise a simulation scheme that assumes the Null H0 is TRUE     
 4.  Repeat the simulation many times and record sample statistic     
 5.  Calculate p-value as the proportion of simulatiomns that yiled a result favorable to the Null H0

So P(hat)(sim) is a flip of a coin 8 times and record the proportion of HEADS at each iteration.    

R for simulation:     

Paul = factor(c(rep("yes", 8), rep("no", 0)), levels = c("yes", "no")

inference(paul, est = "proportion", type = "ht", method = "simulation"     
, success = "yes", null = 0.5, alternatiove = "greater")     

function yields a p-value of 0.0037.     
**The p-value is NOT the probablity of the alternative hypothesisbeing true**    













 



























 