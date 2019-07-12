Week 3.md
Regression with multiple predictors

-> book_mir = lm(weight ~ volume + cover, data = allbacks)
summary(book_mir)

one of the levels of the cover variable is noted on the regression output. And remember that **the one that is noted on the regression output is the non-reference level.** Which means that the hardcover books must be the reference level. 

R-squared to be 92.75%. That means 92.75% of the variability of weight of books can be explained by the volume and cover type.

Coefficients:
              Estimate Std. Error t value Pr(>|t|)    
(Intercept)  197.96284   59.19274   3.344 0.005841 ** 
volume         0.71795    0.06153  11.669  6.6e-08 ***
coverpb     -184.04727   40.49420  -4.545 0.000672 ***

Linear Model
Pred_Weight = 197.96 + 0.72(volume) - 184.05(cover:pb) 
     (pb is the non-reference level.  for refenernce we alsways plug in 0)    

If we wanted to see what this looked like for **only HardCover books** (refenernce)     
Pred_Weight = 197.96 + 0.72 volume - (184.05 * 0) 
Pred_Weight = 197.96 + 0.72 volume = We have simplified the multiple regression down to a simple regression with only one type of book (volume)     

**For Paperback Only** plug in 1 
Pred_Weight = 197.96 + 0.72(volume) - 184.05(cover:pb) * 1    
     (197.96 - 184.05(cover:pb = 13.91)
     Pred_Weight = 13.91 + 0.72(volume)      

Lets look at Regression Parameters: 
Two slopes:
volume : 0.72     
coverpb : -184.04  

for each 1 cm increase in **volume** the model predicts the books to be heaver no averae by 0.72 grams.     

fr coverpb, hardcover is the referece level, so from going from hardcover (refernce) to paperback there is an expected decrease of 184.04 grams.     

Intercept: when **volume** is 0, and Reference (hardcover = 0) is being considered:    
Thus, "hardcover books with no volume are expected on average to weigh 198 grams."     

Example:
paperback book that is  600cm in volume     
Pred_Weight = 197.96 + 0.72(600) - 184.05*1    
   *1 for paperback
   *0  for hardcover as that's the reference  
   = 445.91 grams     

   **ADJUSTED R SQUARED**

   PAIRWISE SCATTER PLOTS:     
   Correlation Coefficient (R) in plot is number at intersection on lower left.  The plot is on the upper right.  **GOOD TO KNOW**     

   The sizes of the Correlation Coefficients relate to the magnatude of correlation.  **ALSO GOOD TO KNOW**  

   The correlation coefficient between these variables is 0.53.     

   R squared, the percentage of variability in poverty explained by female householder is the square of that number or 28%  

   Coefficients:
             Estimate Std. Error t value Pr(>|t|)    
(Intercept)    3.3094     1.8970   1.745   0.0873 .  
female_house   0.6911     0.1599   4.322 7.53e-05 ***

Small Pr(>|t (7.53e-05) means that percentage of femaale householder is a significant indicator of poverty.  

ANOVA    
             Df Sum Sq Mean Sq F value   Pr(>F)    
female_house  1  132.6   132.6   18.68 7.53e-05 ***
Residuals    49  347.7     7.1      

ANOVA allows us to partition the variability in our response variable.     
 So the total measure of the variability in the response variable is sum of squares total that's (132.6 + 347.7) 480.25.

 ![formula](http://latex.codecogs.com/gif.latex?R%5E2%20%3D%20%5Cfrac%7Bexplained%20variability%7D%7Btotal%20variability%7D "R^2 = \\frac{explained variability}{total variability}")

 explained 132.57 / total variability 480.25 = 0.28 or R^2     

Adding White to ANOVA:     
Response: poverty
             Df Sum Sq Mean Sq F value    Pr(>F)    
female_house  1 132.57 132.568 18.7447 7.562e-05 ***
white         1   8.21   8.207  1.1605    0.2868    
Residuals    48 339.47   7.072          

R^2 = (132.57 + 8.31)/ 480.25 = 0.29  

Adjusted R2 =  
1 - [(SSE/SST) * (n-1/n-k-1)] 
k is number of predictors     
Applies a penalty to R squared, for the number of predictors included in the model, and the magnitude of this penalty, is going to depend on how k, the number of predictors compares to n, our sample size.      

**R Squared always increases** with the addition of another variable to the model. 
**Adjust R Squared** will only increae if the added variable is of value.

From above:

1- [(339.47 / 480.25)] / [(51 -1) / 51 - 2- 1)] = 
51 was sample size **given in problem**
k is number of predictors (female_house, white)

= 0.26

k can never be negitive so Adj R^2 is always < R^2
choose models with higher Adj R^2 over others

**Collinearity and Parsimony**

Collinearity: Two predictor variables are said to be collinear when they are correlated with each other.     
Parsimony:  The simplest, best model - Occam's razor     
    The model that has the highest predictive power, however, has the lowest number of variables.     

**Inference for MLR**    

Residuals:
    Min      1Q  Median      3Q     Max 
-54.045 -12.918   1.992  11.563  49.267 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept) 19.59241    9.21906   2.125   0.0341 *  
mom_hsyes    5.09482    2.31450   2.201   0.0282 *  
mom_iq       0.56147    0.06064   9.259   <2e-16 ***
mom_workyes  2.53718    2.35067   1.079   0.2810    
mom_age      0.21802    0.33074   0.659   0.5101    
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01  0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 18.14 on 429 degrees of freedom
Multiple R-squared:  0.2171,  Adjusted R-squared:  0.2098 
F-statistic: 29.74 on 4 and 429 DF,  p-value: < 2.2e-16.     

H0:  B1= B1= B1= Bk = 0     
In other words none of the slopes of the variables are a significant predictor.     
HA atleast 1 on the slopes is different than 0.      

**F-statistic: 29.74 on 4 and 429 DF,  p-value: < 2.2e-16**     
449 DF = n -k- 1     
4 variables
Since P is < 0.05, the model as a whole is significant and reject H).     

QUESTION:  Is whether or not the mother went to high school a significant predictor of the cognitive test scores of children, given all other variables in the model?

H0: B1(mom_hsyes) = 0     
H1: B1 != 0    

mom_hsyes    5.09482    2.31450   2.201   0.0282 * 
Pr(>|t|) = "P-Value" = 0.0282   

Just for kicks:
- always use t-statistic in inference
t statistics = (point estimate - null value) / SE    

point estimate = b1 = slope = 5.09482    
SE = n - k - 1:     
     k is the number of predictors     
     n is the sample size     

For a single predictor the DF is n - 2 (1 for the slope and 1 for the intercept) So a Single Predictor is n - 2 or **n -1- -1**   

 t = (5.09482 - 0)/ 2.315 (from output!!) = 2.201  

 To get the p-value we need df:
  434 - 4 -1 = 429 = df    

  p = pt(2.201, df = 429, lower.tail = FALSE) *2     
  0.028       
  Reject H0 and say mom_hsyes is a significant predictor.     

  **Confidenct Interval:**

  point estimate +- margin of error:

critical value =      
curve 95% and each tail 2.5%
df = 429     
t score = **qt(0.025, df=429)**     
-1.965   Take the allbackssolute value... 1.965    


margin of error = t-statistic * standard error = 1.965 * 2.315    
  =  4.548     

so:
point estimate = slope = 2.53 (from table)
margin of error 4.548     

  confidence interval = 2.53718 +- 4.548   (-2.01, 7.08) 

  Interpretation:   we are 95% confident that, all else being equal, the model predicts that children whose moms worked during the first three years of their lives scored 2.09 points lower to 7.17 points higher than those whose moms did not work.

  **MODEL SELECTION**    
  Picking variables
  "Backwards Elimination" of "Forward Selection":
  Starting wtih full model and eliminating one-by-one, or visa versa.    
  
  We are going to use p-values and adjusted R^2   

  1. start with full model    
  2. Drop one variable at a time and record adj R^2   
  3. Pick model with the **highest increase of adj R^2**
  4. Repeat until none of the models yield an increase in adj R^@.    

            Estimate Std. Error t value Pr(>|t|)    
(Intercept) 19.59241    9.21906   2.125   0.0341 *  
mom_hsyes    5.09482    2.31450   2.201   0.0282 *  
mom_iq       0.56147    0.06064   9.259   <2e-16 ***
mom_workyes  2.53718    2.35067   1.079   0.2810    
mom_age      0.21802    0.33074   0.659   0.5101    
---

Residual standard error: 18.14 on 429 degrees of freedom
Multiple R-squared:  0.2171,  **Adjusted R-squared:  0.2098** 
F-statistic: 29.74 on 4 and 429 DF,  p-value: < 2.2e-16

Full model has **Adjusted R-squared:  0.2098**

using p-value for backwards...
1. start with full model    
2. drop the variable with the highest p-value and refit a smaller model.    
3. repeat until all variables remaining are significant.     

**If you have a categorical variable with multiple levels, you cannot drop part, some of the levels of that variable and keep others.**

So the p-value and adj R^2 will yield different models.  Which to use?

p-value  - If we want to know which predictors are statistically significant.         
 - more common approach.
 - depends on arbitrary 5% significance level.     
adj R^2 - More reliable predictions.

FORWARD SELECTION  

 adj R^2     
1. Start with a single predictor of regressions response v. each explanatory variable.    
2. Pick a model with highest adj R^2  
3. Add remaining variables one at a time and pick model with highest adj R^2        
4. Repeat until the addition of any of the remaining variables deoes not result in a higher adj R^2,


p-value
1. Start with single predictor regressions of response v. explanatory variable .    
2. Pick the variable with the **lowest significant p-value**    
3. Add the remaining variables one at a time to the existing model, and pick the variable with the lowest sig. p-value.  
4. repeat until any of the remaining variables do not have a significant p-value.  


**DIAGNOSTICS FOR MLR**
Conditions:
linear between x and y
residuals nearly nornmal distriburtion of residuals
constant variability of residuals
indepedance of residuals  

 plot (cog_final$risduals ~ cognitive$mom_iq)

 qqnorm(cog_full$residuals)
 hist(cog_full$residuals)
 qqline(cog_full$residuals)
 
 instead of cog_full need to use output from model. cog_final?

 plot(cog_final$residuals ~ cog_final$residuals)
 plot(abs(cog_final$residuals) ~ cog_final$fitted)

 plot(cog_final$residuals)























