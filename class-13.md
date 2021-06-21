## How to run Linear regression in Python scikit-Learn



You know that linear regression is a popular technique and you might as well seen the mathematical equation of linear regression
. But do you know how to implement a linear regression in Python?? If so don’t read this post because this 
post is all about implementing linear regression in Python. There are several ways in which you can do that, you can do linear regression using numpy, scipy,
stats model and sckit learn. But in this post I am going to use scikit learn to perform linear regression.

![image](https://user-images.githubusercontent.com/79086986/122823623-4661eb00-d2e8-11eb-8d49-bc1405a709fe.png)

Scikit-learn is a powerful Python module for machine learning. It contains function for regression, 
classification, clustering, model selection and dimensionality reduction. Today, I will explore the sklearn.
linear_model module which contains “methods intended for regression in which the target value is expected to be a linear combination of the input variables”.

In this post, I will use Boston Housing data set, the data set contains information about the housing
values in suburbs of Boston. This dataset was originally taken from the StatLib library which is maintained at Carnegie Mellon
University and is now available on the UCI Machine Learning Repository. UCI machine learning repository contains many interesting data sets, I encourage you to go through it.

So come on lets have fun with linear regression,

Exploring Boston Housing Data Set
The first step is to import the required Python libraries into Ipython Notebook.

![image](https://user-images.githubusercontent.com/79086986/122823679-5679ca80-d2e8-11eb-99c0-649e6c4a2362.png)

Scikit Learn
In this section I am going to fit a linear regression model and predict the Boston housing prices. I will use the least squares method as the way to estimate the coefficients.

Y = boston housing price(also called “target” data in Python)

and

X = all the other features (or independent variables)


Fitting a Linear Model
I am going to use all 13 parameters to fit a linear regression model. Two other parameters that you can pass to linear regression object are fit_intercept and normalize.

In [20]: lm.fit(X, bos.PRICE)

Out[20]: LinearRegression(copy_X=True, fit_intercept=True, normalize=False)

I am going to print the intercept and number of coefficients.

![image](https://user-images.githubusercontent.com/79086986/122823787-75785c80-d2e8-11eb-8dae-f03fa8d7c604.png)




