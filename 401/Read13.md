# Linear Regressions

## Exploring Boston Housing Data Set

The first step is to import the required Python libraries into Ipython Notebook.

![first](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Explore-1.png)

This data set is available in sklearn Python module, so I will access it using scikitlearn. I am going to import Boston data set into Ipython notebook and store it in a variable called boston.

![sklearn](https://bigdata-madesimple.com/wp-content/uploads/2016/04/sklearn.png)

The object boston is a dictionary, so you can explore the keys of this dictionary.

![boston keys](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-keys.png)

![boston data shape](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-data-shape1.png)

I am going to print the feature names of boston data set.

## Scikit Learn

In this section I am going to fit a linear regression model and predict the Boston housing prices. I will use the least squares method as the way to estimate the coefficients.

Y = boston housing price(also called “target” data in Python)

and

X = all the other features (or independent variables)

![scikitlearn](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Skitlearn-linear-model1.png)

## Fitting a Linear Model

I am going to use all 13 parameters to fit a linear regression model. Two other parameters that you can pass to linear regression object are fit_intercept and normalize.

In [20]: lm.fit(X, bos.PRICE)

Out[20]: LinearRegression(copy_X=True, fit_intercept=True, normalize=False)

![fitting](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Estimated-Coeff.png)

## Predicting Prices

I am going to calculate the predicted prices (Y^i) using lm.predict. Then I display the first 5 housing prices. These are my predicted housing prices.

![plot1](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Prices-vs-predicted-prices.png)

## Training and validation data sets

In practice you wont implement linear regression on the entire data set, you will have to split the data sets into training and test data sets. So that you train your model on training data and see how well it performed on test data.

![training](https://bigdata-madesimple.com/wp-content/uploads/2016/04/train-test-split.png)

## Input:

print “Fit a model X_train, and calculate MSE with Y_train:”, np.mean((Y_train – lm.predict(X_train)) ** 2)

print “Fit a model X_train, and calculate MSE with X_test, Y_test:”, np.mean((Y_test – lm.predict(X_test)) ** 2)

## Output:

Fit a model X_train, and calculate MSE with Y_train: 19.5467584735 Fit a model X_train, and calculate MSE with X_test, Y_test: 28.5413672756

## Residual Plots

Residual plots are a good way to visualize the errors in your data. If you have done a good job then your data should be randomly scattered around line zero. If you see structure in your data, that means your model is not capturing some thing.

![residualplot](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Residual-plot.png)

