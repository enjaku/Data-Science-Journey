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















