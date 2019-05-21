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

##Inference for Comparing Two Paired Means

When two sets of observations are not independent, they are said to be "paired".  

diff = read - write:  create a new variable called "diff". 
To find the average of all the diffs: ![formula](http://latex.codecogs.com/gif.latex?%7B%5Cmu_d_i_f_f%7D "{\\mu\_d\_i\_f\_f}")

Since we don't have access to entire population we can use the sample statistic ![formula](http://latex.codecogs.com/gif.latex?%7B%5Cbar%7Bx%7D_d_i_f_f%7D "{\\bar{x}\_d\_i\_f\_f}")

Set hypothesis: Ho is mu(diff) = 0
                Ha is mu(diff) != 0

Run it per normal.
df = smallest n - 1   

T = standard t-score calculation
        ![formula](http://latex.codecogs.com/gif.latex?T%20%3D%20%5Cfrac%7BObserved%20-%20Null%7D%7BSE%7D "T = \\frac{Observed - Null}{SE}")

![formula](http://latex.codecogs.com/gif.latex?SE%20%3D%20%5Cfrac%20%7Bs%7D%20%7B%5Csqrt%7Bn%7D%7D "SE = \\frac {s} {\\sqrt{n}}")

Making decisions based on the p-value is simple. Compare the p-value to the significance level and if it's lower, reject the null hypothesis, and conclude that the data provide convincing evidence for the alternative hypothesis.

##Power
Find the appropriate sample size that we can be 80% sure that we would detect any practically important effects of the drug.

The probability of rejecting H0 | H0 is false.

The probability of **not** making a Type 2 error

If you increase alpha (level of significance) you increase the Power, but also the Probability of a Type 1 error. 

Increasing sample size decreases overlap of curves and increases power "The probability of **not** making a Type 2 error."

##Comparing Many Means
When we want to compare three or more we use ANOVA and F-Statistics.  

H0 says that all the means are equal.   

HA says that at least one of the means is different.  **It does not state which mean is different**    

![formula](http://latex.codecogs.com/gif.latex?F%3D%5Cfrac%7Bvariability%20BETWEEN%20groups%7D%7Bvariability%20WITHIN%20groups%7D "F=\\frac{variability BETWEEN groups}{variability WITHIN groups}")

Obtaining a large F statistic requires that the variability **between** groups be much larger than the variability **within** groups.   

##AVOVA
The numerical value is always the RESPONSE variable in ANOVA.

Take overall variability and partion into two) **"Between Group Variability", aka the Group Row** and **"Within Group Variability", aka the Error Row**.  They seem to just disgard Within Group Variability as a trash statistic.  Kahn would be pissed :)

Some vocabulary:   
**Sum of Squares Total (SST)**: 
        -The some of the squares of ALL of the samples.  
        -Very similar to Variance but not scalled by sample size.  
        -The SUM of the squared deviation from the **GRAND MEAN** of the RESPNSE VARIABLE.  (She forgot that fucking part!!).    
        -This is the total variability in the response variable, which is also the sum of the two group variables... thank you Kahn!!

**Sum of Squares Groups (SSG)**:
        -measures the variability **between groups** and can be thought of as the variability in the response variable explained by explanatory variable in the analysis.  
     
![formula](http://latex.codecogs.com/gif.latex?SSG%20%3D%20%5Csum%20%7Bn_j%7D%28%7B%5Cbar%7By%7D_j%7D-%7B%5Cbar%7By%7D%29%5E2 "SSG = \\sum {n\_j}({\\bar{y}\_j}-{\\bar{y})^2")

 -The n of j will obviously be different for each group.

 **Sum of Squares Error (SSE)**
 - Measeures the variability **within groups**   
 -  Cheat:  SSE = SST - SSG

***Degrees of Freedom part***

- Total Df = n-1
- Group Df = Number of groups - 1
- Error Df = Total Df - Group Df 

***Mean Squares***
- See notebook for explaination of columns for all of this shit.
- Mean Square Group (MSG) = SSG / Group Df  
- Mean Square Error (MSE) = SSE / Error Df 

**Finally the F-Statistic:**

![formula](http://latex.codecogs.com/gif.latex?F%20Statistic%3D%5Cfrac%7BMSG%7D%7BMSE%7D "F Statistic=\\frac{MSG}{MSE}")

**Find the P-Value and conclude the journey:**
- The p-value in this context is the probability of at least as large a ratio between the between and within group variabilities, if in fact the means of all groups are equal.    

- p-value is the probability of observed or more extreme outcome given the null hypothesis is true.    

- Calculated as the area under the F distribution. **And the F statistic has two degrees of freedom, _degrees of freedom group_ and _degrees of freedom error_.**   

- Only deals with far-upper tail of the curve.

This gives you the P-Value
**R pf function  _>pf(F-statistic, MSG, MSE, lower.tail = FALSE)_**

**Conlusion**
- If the P-Value is small we reject the H0 "If the P is low, the Null has to go"

##Conditions for ANOVA
Independence both WITHIN and BETWEEN groups. 
    - n(j) is <10% 
Approximate normality
    - you can check with normal probability plots.  (Upward slopping line plot)
Equal variance accross groups: aka, "homoscedastic groups" - big word :)   
    - box plots work for this.  How big are the IQRs?


##Multiple Comparisions

ANOVA just tells us that there is a difference, but does not indicate where that difference is.

To see if two means are different we do a T-test, but incure a Type 1 error.

Bonferroni correction - Use a more stringent gisnificance level.   
    - two step process.  

1. Find the number of comparrisons:
     
![formula](http://latex.codecogs.com/gif.latex?K%3D%5Cfrac%7Bk%28k-1%29%7D%7B2%7D "K=\\frac{k(k-1)}{2}")

2. Correct your original alpla

![formula](http://latex.codecogs.com/gif.latex?%7B%5Calpha_%2A%7D%20%3D%20%5Cfrac%7B%5Calpha%7D%7BK%7D%20 "{\\alpha\_\*} = \\frac{\\alpha}{K} ")

**Make Adjustment to SE**

**SE = SQRT {(MSE/n1) + (MSE/n2)}**

**Df is going to be Error Df**

Pick two groups and calculate the T-score:

T = {xbar (1 group) - xbar (another group)} - 0(null value) / **SE** *(see SE calcl above)*

In example the T=score was 5.365 with a Df from the ANOVA table of 791 *(Error Df)*

Next: Find P-value:
T-score: 5.365   
Df: 791   
Draw the curve   

**R code:  > 2* pt(5.365, df = 791, lower.tail = FALSE)**  

Remember to multiply by 2x because its a Hypothosis test and we need to account for BOTH ends, e.g. = v !=.  

Also remember we're using the Bonferrioni corrected alpha, which is smaller.  


























































