### Week 1

These are notes of the first week of Inferential Statistics.  I'm utting them in a markdown document and loading up to GitHub as an experient in workflow.

Let the fun begin.

- Samply Variability - estimates how one sample varies from another
- Samplying Distribution
    + Take sample statistics, e.g. mean, mode, etc., from several different samples from the population and then look at them as a group... finding the **SampLING Distribution**. 
    + Standard Deviation of the Sample Means (SampLING Distribution) is called the **Standard Error$**.  **sd of x(bar) = (SE)**
    + As n increses the Standard Error will decrease.

While individial populations are "very variable", it is unlikey that sample means will be "very variable".  The histogram of the sampLING distribtion is a lot skinnier than the population histogram.

The higher the sample size that we take from the population, the less variable the means of the samples, e.g. they get tall and very skinny.

**The Central Limit Theory** says that The distribution of the sample statistic is nearly normal (bell shaped), centered at the population mean, with a standard deviation equal to the population standard deviation divided by the sqr root of the sample size.

**CLT** requirements:
- Independence

- if sampling **without replacement** the sample size (n) < 10% of the population.  *The reason is that within large samples there is often less independence, a family getting sampled in a town of 1000 pop*

- If population is not normal, e.g., skewed we need a larger sample size, generally > 30.  The larger the sample size the closer to normal the sampLINGdistribution becomes.  Normal samples lend themselves to probability calculations.  **"The more the skew the mores sample size you need for the CLT to kick-in"**.

**Central Limit Theory & Samplying**
Cannot use a Z-score on skewed data.
    *For review: The Z-score-score (aka "standard score") is the number of standard deviations from the mean a data point is*
        *Need to take Z-score and look up in table to find the probablility percentage associated with it.*  *R function is pnorm, also see dnorm (density) qnorm (qualtile) and rnorm (random deviates)*.

x(bar) The Sample Mean.
To find the Z-score make sure that you divide by the Standard Error and NOT the sigma of the standard deviation of the population.
    -We measure the variability of **individual observations** with standard deviations. x in the numerator
    -We measure the variability of **sample means** with standard errors. x(bar) in the numerator.

**Confidence Intervals of the Mean**
 = A plausable range of values for the population parameter is called a Confidence Interval.

 So if you have x(bar) best guess for unknown true population mean
 - keep in mind 68/95/97.5 rule
 - So 95% Confidence Interval is the x(bar) (+ or -) two standard errors aka "Margin of Error"

 **The Confidence Interval for Population Mean** is the Sample Mean (x(bar)), +- the Standard Error  (critical value that corresponds the the XX% of the normal distribution x standard error of the sampLING distribution)
    Conditions:
        - Interpendance
        - Sample size < 10% of population
        - n >= 30, larger if the population is skewed.

If you want to find the exact cut off off for a 95% confidence level...
    - draw curve and mark above and below the mean.
    - then 1-(0.95)/2 gives us 0.025 on either side.
    - to find the z-score from the table we can use **qnorn**
        > qnorm (0.025)  yields -1.96.
    - So we can say that the critical value is between 1.96 and -1.95 with 95% confidence.

   **Accuracy ane Precision**
   Normally we choose the confidence interval that we want and then calulate the critical values.
   - Common confidence intervals are 90%, 95% 98% and 99%
   - If we want to increase **accuracy** we need to increase the confidence inerval.  The drawback is that the **precision** goes down.  Think of a weather report that says that it will be -10 deg to 110 degrees tomorrow.  Yup, pretty accurate but not very useful, e.g. precise.
   - If you want both, you need to **increase the sample size**; which will shrink of SE and our margin of error.

**The margin of error** is the range of values below and above the sample statistic in a confidence interval.

Required Sample Size for a given Margin of Error (ME).  We're going to work backwards now.

Checking UpLoad of File.





    



