
# Car-Price-Project
## Linear Regression Problem

you will be introduced to a problem statement on car prices where you have to build a multiple linear regression model to solve it.  Understand the problem statement carefully

## Problem Statement
This is a programming assignment wherein you have to build a multiple linear regression model to predict car prices.

A Chinese automobile company, Geely Auto, aspires to enter the US market by setting up their manufacturing unit there and producing cars locally to give competition to their US and European counterparts. 

 

They have contracted an automobile consulting company to understand the factors on which the pricing of cars depends. Specifically, they want to understand the factors affecting car pricing in the American market, as they may differ from the Chinese market.

**The company wants to know the following things:**

- Which variables are significant in predicting the price of a car?
- How well do those variables describe the price of a car?

Based on various market surveys, the consulting firm has gathered a large data set of different types of cars across the American market. 

**Business Goals**

You are required to model the price of cars with the available independent variables. The management will use be using this model to understand exactly how the prices vary with the independent variables. Accordingly, they can change the design of the cars, the business strategy, etc., to meet certain price levels. Further, the model will allow the management to understand the pricing dynamics of a new market.

 

**Data Preparation**

There is a variable named CarName that comprises two parts: the first word is the name of the car company, and the second is the car model. For example, Chevrolet Impala has ‘Chevrolet’ as the car company name and ‘Impala’ as the car model name. You need to consider only the company name as the independent variable for model building.

 

**Model Evaluation**

When you are done with model building and residual analysis and have made predictions on the test set, ensure that you use the following two lines of code to calculate the R-squared score on the test set:
 

- from sklearn.metrics import r2_score
  
  r2_score(y_test, y_pred)
 

- Where y_test is the test dataset for the target variable, and y_pred is the variable containing the predicted values of the target variable on the test set.

 

- Do not forget to perform this step as the R-squared score on the test set holds some marks. The variable names inside the ‘r2_score’ function can vary based on your chosen variable names.
 

 
## Downloads

You can download the data set file from the link given below:

[here.](https://www.kaggle.com/datasets/dushyantnagar7806/car-price)


## FAQ

#### Question 1  Explain the linear regression algorithm in detail.

Answer 1  Linear regression is a supervised machine learning algorithm used for predicting a continuous target variable based on one or more input features. It establishes a linear relationship between the independent variables (features) and the dependent variable (target) by fitting a straight line to the data.

The goal of linear regression is to find the best-fitting line that minimizes the difference between the predicted values and the actual values. The line is defined by an equation of the form:

   - y = b0 + b1x1 + b2x2 + ... + bn*xn

#### Question 2  What are the assumptions of linear regression regarding residuals?

Answer 2   a.	Normality assumption: It is assumed that the error terms, ε(i), are normally distributed.
b.	Zero mean assumption: It is assumed that the residuals have a mean value of zero, i.e., the error terms are normally distributed around zero.
c.	Constant variance assumption: It is assumed that the residual terms have the same (but unknown) variance, σ². This assumption is also known as the assumption of homogeneity or homoscedasticity.
d.	Independent error assumption: It is assumed that the residual terms are independent of each other, i.e. their pair-wise covariance is zero.


	
#### Question  3.	What is the coefficient of correlation and the coefficient of determination?

Answer 3    Coefficient of correlation gives the value of correlation between two variables indicating that when one of the variables is changing, how much it is impacting the other variable. Coefficient of determination, on the other hand, is just the coefficient of correlation squared. For simple linear regression, it is simply the R-squared value.



#### Question 4.	Explain the Anscombe’s quartet in detail.?

Answer 4  You should never just run a regression without having a good look at your data because simple linear regression has quite a few shortcomings:
1.	It is sensitive to outliers
2.	It models the linear relationships only
3.	A few assumptions are required to make the inference
These phenomena can be best explained by the Anscombe's Quartet, shown below:

![image](https://github.com/dushyantnagar7806/Car-Price-Project/assets/109071505/9af8c106-632a-46ab-bf44-fec3890b7bc3)

As we can see, all the four linear regression are exactly the same. But there are some peculiarities in the datasets which have fooled the regression line. While the first one seems to be doing a decent job, the second one clearly shows that linear regression can only model linear relationships and is incapable of handling any other kind of data. The third and fourth images showcase the linear regression model's sensitivity to outliers. Had the outlier not been present, we could have gotten a great line fitted through the data points. So, we should never ever run a regression without having a good look at our data.




#### Question 5.	What is Pearson’s R?

Answer 5   If two variables are correlated, it is very much possible that they have some other sort of relationship and not just a linear one.
But the important point to note here is that there are two correlation coefficients that are widely used in regression. One is the Pearson's R correlation coefficient which is the correlation coefficient you've studied in the linear regression model. This correlation coefficient is designed for linear relationships and it might not be a good measure for if the relationship between the variables is non-linear. The other correlation coefficient is Spearman's R which is used to determine the correlation if the relationship between the variables is not linear. So even though, Pearson's R might give a correlation coefficient for non-linear relationships, it might not be reliable. For example, the correlation coefficients as given by both the techniques for the relationship y = X³ for 100 equally separated values between 1 and 100 were found out to be:
Pearson′s R ≈ 0.91
Spearman′s R ≈ 1
And as we keep on increasing the power, the Pearson's R value consistently drop whereas the Spearman's R remains robust ar 1. For example, for the relationship y=X10 for the same data points, the coefficients were:
Pearson′s R ≈ 0.66
Spearman′s R ≈ 1
So, the takeaway here is that if you have some sense of the relationship being non-linear, you should look at Spearman's R instead or Pearson's R. It might happen that even for a non-linear relationship, the Pearson's R value might be high, but it is simply not reliable. 





#### Question 6.	What is scaling? Why is scaling performed? What is the difference between normalized scaling and standardized scaling?

Answer 6   Scaling is the process of bringing all the variables to a same scale. Scaling is performed mostly during model building processes to bring everything to the same scale. 

In normalized scaling, we use the maximum and the minimum values of a particular column to perform the scaling. For any datapoint ‘X’ in a column ‘C’, this scaling is performed using the formula: X – min(C)/max(C) – min(C).

Standardised scaling, on the other hand, brings all the data points in a normal distribution with mean zero and standard deviation one. It is performed using the formula: X – mean(C)/SD(C)




#### Question 7.	You might have observed that sometimes the value of VIF is infinite. Why does this happen?

Answer 7    Recall that the formula for VIF is given as:

VIF = 1/(1-R²)

Now, when you’re calculating the VIF for one independent variable using all the other independent variables, if the R² value comes out to be 1, the VIF will become infinite. This is quite possible when one of the independent variables is strongly correlated with many of the other independent variables.




#### Question 8.	What is the Gauss-Markov theorem?

Answer 8  The Gauss-Markov theorem, also known as the Gauss-Markov assumption or the Gauss-Markov conditions, is a fundamental result in statistics and econometrics. It establishes the conditions under which the ordinary least squares (OLS) estimators in linear regression are considered the best linear unbiased estimators (BLUE).



#### Question 9.	Explain the gradient descent algorithm in detail.

Answer 9   [here.](https://www.analyticsvidhya.com/blog/2020/10/how-does-the-gradient-descent-algorithm-work-in-machine-learning/)


#### Question 10.	What is a Q-Q plot? Explain the use and importance of a Q-Q plot in linear regression.

Answer 10    Q-Q plots are also known as Quantile-Quantile plots. As the name suggests, they plot the quantiles of a sample distribution against quantiles of a theoretical distribution. Doing this helps us determine if a dataset follows any particular type of probability distribution like normal, uniform, exponential


# Article
1. **Everything you need to Know about Linear Regression!**
	[here.](https://www.analyticsvidhya.com/blog/2021/10/everything-you-need-to-know-about-linear-regression/)

2. **Q-Q plot – Ensure Your ML Model is Based on the Right Distribution**
   	[here.](https://www.analyticsvidhya.com/blog/2021/09/q-q-plot-ensure-your-ml-model-is-based-on-the-right-distributions/)
   
