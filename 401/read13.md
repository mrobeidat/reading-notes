
# Linear Regressions

## How to Run Linear Regression in Python 

***There are several ways in which you can do that, you can do linear regression using numpy, scipy, stats model and sckit learn.*** 

* ### Scikit-learn 

**is a powerful Python module for machine learning. It contains function for regression, classification, clustering, model selection and dimensionality reduction.**  

### Exploring Boston Housing Data Set  

* The first step is to import the required Python libraries into Ipython Notebook. 

![import](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Explore-1.png) 

* This data set is available in sklearn Python module, so we will access it using scikitlearn. 

![access](https://bigdata-madesimple.com/wp-content/uploads/2016/04/sklearn.png) 

* The object boston is a dictionary, so you can explore the keys of this dictionary. 

![explore the kyes](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-keys.png) 

![explore the kyes](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-data-shape1.png) 

* print the feature names of boston data set. 

![print](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-features.png)

* In this data set I have 506 instances(rows) and 13 attributes or parameters(columns).  

![check](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-description.png) 

* convert boston.data into a pandas data frame. 

![convert](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Pandas-DataFrame.png) 

* replace those numbers with the feature names. 

![rplace](https://bigdata-madesimple.com/wp-content/uploads/2016/04/bos-columns.png) 

*boston.target contains the housing prices. 

![contains](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Boston-target.png) 

* add these target prices to the bos data frame.

![add](https://bigdata-madesimple.com/wp-content/uploads/2016/04/RAD.png)

### Scikit Learn  

**fit a linear regression model and predict the Boston housing prices. Use the least squares method as the way to estimate the coefficients.** 

* Y = boston housing price(also called “target” data in Python)

* X = all the other features (or independent variables) 

**import linear regression from sci-kit learn module.** 

![import1](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Skitlearn-linear-model1.png) 

**Important functions to keep in mind while fitting a linear regression model are:**

* lm.fit() -> fits a linear model

* lm.predict() -> Predict Y using the linear model with estimated coefficients

* lm.score() -> Returns the coefficient of determination (R^2). A measure of how well observed outcomes are replicated by the model, as the proportion of total variation of outcomes explained by the model.  

### Fitting a Linear Model 

**use all 13 parameters to fit a linear regression model. Two other parameters that you can pass to linear regression object are fit_intercept and normalize.** 

![parameters](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Estimated-Coeff.png)

**then construct a data frame that contains features and estimated coefficients.** 

![dataframe](https://bigdata-madesimple.com/wp-content/uploads/2016/04/pd-data-frame.png)

**from the data frame that there is a high correlation between RM and prices. Lets plot a scatter plot between True housing prices and True RM.** 

![dataframe1](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Scatter-plot.png)

![plt](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Relationship-between-RM-and-Price.png) 

### Predicting Prices 

**calculate the predicted prices (Y^i) using lm.predict. Then display the first 5 housing prices. These are my predicted housing prices.** 

![cal](https://bigdata-madesimple.com/wp-content/uploads/2016/04/lm-predict.png) 

**plot a scatter plot to compare true prices and the predicted prices.** 

![plt1](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Scatter-plot-in-the-pandas.png)

![plt2](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Prices-vs-predicted-prices.png) 

* Lets calculate the mean squared error. 

![cal1](https://bigdata-madesimple.com/wp-content/uploads/2016/04/MSE-full.png) 

![cal2](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Linear-regression-and-fitting.png)

![cal3](https://bigdata-madesimple.com/wp-content/uploads/2016/04/MSE-prat1.png) 

### How to do train-test split: 

**divide your data sets randomly. Scikit learn provides a function called train_test_split to do this.**

![divide](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Xtrain-and-Xtest.png)

**build a linear regression model using my train-test data sets.**

![build](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Linear-reg.png)

* Input:

        print “Fit a model X_train, and calculate MSE with Y_train:”, np.mean((Y_train – lm.predict(X_train)) ** 2)

        print “Fit a model X_train, and calculate MSE with X_test, Y_test:”, np.mean((Y_test – lm.predict(X_test)) ** 2)

* Output:

        Fit a model X_train, and calculate MSE with Y_train: 19.5467584735 Fit a model X_train, and calculate MSE with X_test, Y_test: 28.5413672756


* Residual Plots 

![plt5](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Residual-plot.png) 
