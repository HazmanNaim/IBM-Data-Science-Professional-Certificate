# Module 1 : Importing Datasets
## 1.1 Accessing Databases with Python

Python program communitace with DBMS using API calls

API - set of function to get access to some type of service
SQL API-API for the DBMS

To pass SQL statements to the DBMS, an application program calls functions in the API, and it
calls other functions to retrieve query results and status information from the DBMS.

What is DB-API?
Python standard API to access relational database.

It is a standard that allows you to write a single program that works with multiple
kinds of relational databases instead of writing a separate program for each one.
So, if you learn the DB-API functions, then you can apply that knowledge to use any database
with Python.

DB2 Warehouse on cloud - ibm_db
Compose for MySQL - MySQL connector/Python
Compose for PostgreSQL - psycopg2
Compose for MongoDB - PyMongo

The two main concepts in the Python DB-API are connection objects and query objects.
You use connection objects to connect to a database and manage your transactions.
Cursor objects are used to run queries.
You open a cursor object and then run queries.
The cursor works similar to a cursor in a text processing system where you scroll down
in your result set and get your data into the application.
Cursors are used to scan through the results of a database.

What are connection methods?
The cursor() method returns a new cursor object using the connection.
The commit() method is used to commit any pending transaction to the database.
The rollback() method causes the database to roll back to the start of any pending transaction.
The close() method is used to close a database connection.

Let's walk through a Python application that uses the DB-API to query a database.
First, you import your database module by using the connect API from that module.
To open a connection to the database, you use the connection function and pass in the
parameters that is, the database name, username, and password.
The connect function returns connection object.
After this, you create a cursor object on the connection object.
The cursor is used to run queries and fetch results.
After running the queries using the cursor, we also use the cursor to fetch the results
of the query.
Finally, when the system is done running the queries, it frees all resources by closing
the connection.
Remember that it is always important to close connections to avoid unused connections taking
up resources.

## 1.2 Lesson Summary
In this lesson, you have learned how to:
- Define the Business Problem: Look at the data and make some high-level decision on what kind of analysis should be done
- Import and Export Data in Python: How to import data from multiple data sources using the Pandas library and how to export files into different formats.
- Analyze Data in Python: How to do some introductory analysis in Python using functions like dataframe.head() to view the first few lines of the dataset, dataframe.info() to view the column names and data types.

# Module 2 : Data Wrangling
## 2.1 Pre-processing Data in Python
Data preprocessing is a necessary step in data analysis. It is the process of converting or mapping data from one raw form into another format to make it ready for further analysis.

Data preprocessing is often called data cleaning or data wrangling.

Why?
- Identify and handle missing values
- Data formatting
- Data normalization (centering/scaling) - bring all data to similar range for useful comparison
- Data binning - creates bigger categories from a set of numerical values. It is particularly useful for comparison between groups of data.
- Turning vategorical values to numeric variables

Python works by column.

## 2.2 Dealing with Missing Values in Python
What is missing values?
When no data value is stored for feature for a particular observation, we say this feature has a missing value. Usually missing value in data set appears as question mark and a zero or just a blank cell or NaN.

How to deal?
1. Check with the data collection source 
- find the collector of data and find correct value.
2. Drop the missing values 
- drop the variable, drop the data entry 
- make sure less impact
3. Replace the missing values 
- Replace with average (of similar datapoints)
- Replace with frequency (if not number)
- Replace it based on other functions
4. Leave it as missing data

How to drop missing values in Python?
dataframes.dropna()
axis = 0 drops entire row
axis = 1 drops entire column
e.g df.dropna(subset=["price"], axis=0, inplace=True)

add inplace = True in the dropna function to modify the dataframe

How to replace missing values in Python?
dataframe.replace(missing_value, new_value):
e.g To replace missing values as the mean of column:
mean = df["normalized-losses"].mean()
df["normalized-losses"].replace(np.nan, mean)

How to deal?
1. Check with the data collection source
- drop the missing values
0 replace the missing values
2. Leave it as missing data

## 2.3 Data Formatting in Python
Data formatting : bringing data into a common standard ofexpression that allows users to make meaningful comparisons. As a part of dataset cleaning, data formatting ensures the data is consistent and easily understandable.

Sometimes, the wrong data type is assigned to a feature.

dtype should be let say float but it is assigned to object.

data types in pandas:
- Objects
- Int64
- Float64

Check using dataframe.dtypes() method
To convert, use dataframe.astype()

e.g Convert data type to integer in column "price"
df["price"] = df["price"].astype("int")

Data Normalization in Python

Uniforming the features value with different range

normalization enables a fair comparison between the different features, making sure they have the same impact.

age = [20,40,60]
income = [10000,20000,30000]

So, these two features are in very different ranges.
When we do further analysis, like linear regression for example, the attribute income will intrinsically
influence the result more due to its larger value.

Nromalize to remove the bias.
age = [0.2,0.3,0.4]
income = [0.2,0.04,1]

Similar value range, similar intrinsic influence on analytical model

Approaches for normalization:
- Simple Feature Scaling
- Min-Max
- Z-score (standard score)

## 2.4 Binning in Python
Binning is when you group values together into bins. For example, you can bin “age” into [0 to 5], [6 to 10], [11 to 15] and so on.

Sometimes, binning can improve accuracy of the predictive models.

In addition, sometimes we use data binning to group a set of numerical values into a
smaller number of bins to have a better understanding of the data distribution.

Use histograms to visualize binned data

## 2.5 Turning Categorical Variables into Quantitative Variables in Python
Most statistical models cannot take in objects or strings as input and for model training only take the numbers as inputs.

we set the corresponding value to one in the new feature. The rest of the features are set to zero.

This technique is often called "One-hot encoding.

In Pandas, we can use get_dummies method to convert categorical variables to dummy variables.

## 2.6 Module 2 Lesson Summary
- Identify and Handle Missing Values: Drop rows with incomplete information and impute missing data using the mean values.

- Understand Data Formatting: Wrangle features in a dataset and make them meaningful for data analysis.

- Apply normalization to a data set: By understanding the relevance of using feature scaling on your data and how normalization and standardization have varying effects on your data analysis.

# Module 3 : Exploratory Data Analysis
## 3.1 Exploratory Data Analysis
Approach to analyze data in order to
summarize main characteristics of the data.

Uncover relationships between different variables

Extract important variables for the problem
we're trying to solve.

What are the characteristics that have the most impact on the car price??

## 3.2 Descriptive Statistics
Important to explore your data before building complicated models.

Descriptive statistical analysis helps to describe basic features of a data set, and
obtains a short summary about the sample and measures of the data.

Use pandas describe()

Summarize catagorical data by using value_counts() method.

Use box plots to visualize numerical data

For continuos variables in our data, use scatter plot.

Typically set the predictor variable on the x-axis or
horizontal axis, and we set the target variable on the y-axis or vertical axis.

## 3.3 GroupBy in Python
Groupby() method

Is there any relationship between the different types of drive system, forward, rear, and four-wheel drive, and the price of the vehicles?

In Pandas, this can be done using the group by method. The group by method is used on categorical variables, groups the data into subsets according to the different categories of that variable. You can group by a single variable or you can group by multiple variables by passing in multiple variable names.

To make it easier to understand, we can transform this table to a pivot table by using the pivot method. In the previous table, both drive wheels and body style were listening columns. A pivot table has one variable displayed along the columns and the other variable displayed along the rows.
Just with one line of code and by using the Panda's pivot method, we can pivot the body style variable so it is displayed along the columns and the drive wheels will be displayed along the rows.

Another way to represent the pivot table is using a heat map plot. Heat map takes a rectangular grid of data and assigns a color intensity based on the data value at the grid points. It is a great way to plot the target variable over multiple variables and through this get visual clues with
the relationship between these variables and the target.

## 3.4 Correlation
Correlation is a statistical metric for measuring to what extent different variables are interdependent. In other words, when we look at two variables over time, if one variable changes how does this affect change in the other variable?

It is important to know that correlation doesn't imply causation. In data science we usually deal more with correlation.

Use regplot in seaborn

## 3.5 Correlation - Statistics
Pearson Correlation: Measure the strength of the correlation between two features.

Give two values:
- the correlation coefficient
- the P-value.

Correlation coefficient tells how strong the relationship between variables.

P-value tells how certain we are about the correlation.
Ccorrelation coefficient is approximately.8, and this is close to 1. So there is a strong positive correlation. P-value is very small, much smaller than.001. Idicate strong certainity

Taking all variables into account, we can now create a heatmap that indicates the correlation between each of the variables with one another.
The color scheme indicates the Pearson correlation coefficient, indicating the strength of the correlation between two variables.

## 3.6 Association between two Categorical Variables: Chi Square
When dealing with the relationships between
two categorical variables, we can’t use the same correlation method for continuous variables, we will have to employ the use of chi square test for the association.

Chi-square test is intended to test how likely it is that an observed distribution
is due to chance.

How well the observed distribution
of data fits with the distribution that is expected if the variables are independent.

The Chi-square tests a null hypothesis that the variables are independent. The test compares
the observed data to the values that the model expects if the data was distributed in different
categories by chance.

Anytime the observed data doesn't fit within the model of the expected values, the probability that the variables are dependent becomes stronger, thus proving the null hypothesis incorrect.

The Chi-square does not tell you the type
of relationship that exists between both variables, but only that a relationship exists.

## 3.7 Module 3 Lesson Summary
- Describe Exploratory Data Analysis: By summarizing the main characteristics of the data and extracting valuable insights.
- Compute basic descriptive statistics: Calculate the mean, median, and mode using python and use it as a basis in understanding the distribution of the data.
- Create data groups: How and why you put continuous data in groups and how to visualize them.
- Define correlation as the linear association between two numerical variables: Use Pearson correlation as a measure of the correlation between two continuous variables
- Define the association between two categorical variables: Understand how to find the association of two variables using the Chi-square test for association and how to interpret them.

# Module 4 : Model Development
## 4.1 Model Development
A model or estimator can be thought of as
a mathematical equation used to predict the value given one or more other values.

Relating one or more independent variables or features to dependent variables.

Usually, the more relevant data you have,
the more accurate your model is.

## 4.2 Linear Regression and Multiple Regression
A model or estimator can be thought of as
a mathematical equation used to predict the value given one or more other values.

Relating one or more independent variables or features to dependent variables.

Usually, the more relevant data you have,
the more accurate your model is.

## 4.3 Model Evaluation using Visualization
Regression plots are a good estimate of the relationship between two variables, the strength of the correlation, and the direction of the relationship (positive or negative).
The horizontal axis is the independent variable.
The vertical axis is the dependent variable.
Each point represents a different target point.
The fitted line represents the predicted value.

Use regplot from the seaborn library.

The parameter x is the name of the column that
contains the independent variable or feature.
The parameter y, contains the name of the column that
contains the name of the dependent variable or target.
The parameter data is the name of the dataframe.

The residual plot represents the error between the actual value.
Examining the predicted value and actual value we see a difference.
We obtain that value by subtracting the predicted value,
and the actual target value.
We then plot that value on
the vertical axis with the independent variable as the horizontal axis.

Looking at the plot gives us some insight into our data.
We expect to see the results to have zero mean,
distributed evenly around the x axis with similar variance.
There is no curvature.
This type of residual plot suggests a linear plot is appropriate.

Nonlinear function if the residuals are not randomly separated.

Use seaborn to create a residual plot.
First, "import seabourn."
We use the "residplot" function.
The first parameter is a series of dependent variable or feature.
The second parameter is a series of dependent variable or target.

## 4.4 Polynomial Regression and Pipelines
What do we do when a linear model is not the best fit for our data?

The polynomial regression. We transform our data into a polynomial, then use linear regression to fit the parameter.

Pipelines are a way to simplify your code.

Polynomial regression is a special case of the general linear regression. This method is beneficial for describing curvilinear relationships.

Curvilinear relationship : It's what you get by squaring or setting higher order terms of the predictor variables in the model transforming the data.

We can simplify our code by using a pipeline library.
There are many steps to getting a prediction.
For example, normalization, polynomial transform, and linear regression.
We simplify the process using a pipeline.
Pipeline sequentially perform a series of transformations.
The last step carries out a prediction.

## 4.5 Measures for In-Sample Evaluation
These measures are a way to numerically determine how good the model fits on our data.

Two important measures that we often use to determine the fit of a model are: Mean Square
Error (MSE), and R-squared.

To measure the MSE, we find the difference between the actual value y and the predicted
value yhat then square it.

To find the MSE in Python, we can import the “mean_Squared_error” from “scikit-learn.metrics”.
The “mean_Squared_error” function gets two inputs: the actual value of target variable
and the predicted value of target variable.

R-squared is also called the coefficient of determination. It’s a measure to determine
how close the data is to the fitted regression line. So how close is our actual data to our
estimated model?

We find the R-squared value in Python by using the score method, in the linear regression
object.

## 4.6 Prediction and Decision Making
How do we determine our model is correct?

Always use visualization, numerical measures for evaluation, and comparing between different models.

## 4.7 Module 4 Lesson Summary
- Define the explanatory variable and the response variable: Define the response variable (y) as the focus of the experiment and the explanatory variable (x) as a variable used to explain the change of the response variable. Understand the differences between Simple Linear Regression because it concerns the study of only one explanatory variable and Multiple Linear Regression because it concerns the study of two or more explanatory variables.
- Evaluate the model using Visualization: By visually representing the errors of a variable using scatterplots and interpreting the results of the model.
- Identify alternative regression approaches: Use a Polynomial Regression when the Linear regression does not capture the curvilinear relationship between variables and how to pick the optimal order to use in a model.
- Interpret the R-square and the Mean Square Error: Interpret R-square (x 100) as the percentage of the variation in the response variable y  that is explained by the variation in explanatory variable(s) x. The Mean Squared Error tells you how close a regression line is to a set of points. It does this by taking the average distances from the actual points to the predicted points and squaring them.

# Module 5 : Model Evaluation
## 5.1 Model Evaluation and Refinement
Model evaluation tells us how our model performs in the real world.

In-sample evaluation tells us how well our model fits the data already given to train it.
It does not give us an estimate of how well the train model can predict new data.

The solution is to split our data up,
use the in-sample data or training data to train the model.
The rest of the data, called Test Data,
is used as out-of-sample data.
This data is then used to approximate, how the model performs in the real world.

We use the test data to get an idea how our model will perform in the real world.
When we split a dataset,
usually the larger portion of data is used for
training and a smaller part is used for testing.

We use training set to build a model and discover predictive relationships.
We then use a testing set to evaluate model performance.
When we have completed testing our model,
we should use all the data to train the model.

Use scikit-learn package for splitting datasets, is the train-test-split function.

Generalization error is a measure of how well
our data does at predicting previously unseen data.
The error we obtain using our testing data is an approximation of this error.

All our error estimates are relatively close together,
but they are further away from the true generalization performance.
To overcome this problem, we use cross-validation.
One of the most common out of sample evaluation metrics is cross-validation.

In this method, the dataset is split into K equal groups.
Each group is referred to as a fold.

## 5.2 Overfitting, Underfitting and Model Selection
How to pick the best polynomial order and problems that arise when selecting the wrong order polynomial.

If we increase the order of the polynomial, the model fits better, but the model is still not flexible enough and exhibits underfitting. If we increase the order of the polynomial, the model fits better, but the model is still not flexible enough and exhibits underfitting.

Increasing it to a 16th order polynomial, the model does extremely well at tracking the training point but performs poorly at estimating the function. This is especially apparent where there is little training data. The estimated function oscillates not tracking the function. This is called overfitting,
where the model is too flexible and fits the noise rather than the function.

## 5.3 Ridge Regression Introduction
Ridge regression is a regression that is employed in a Multiple regression model when Multicollinearity occurs. Multicollinearity is when there is a strong relationship among the independent variables. Ridge regression is very common with polynomial regression.

## 5.4 Ridge Regression
Ridge regression prevents overfitting.

Ridge regression controls the magnitude of
these polynomial coefficients by introducing the parameter alpha. Alpha is a parameter we select before fitting or training the model.

As alpha increases, the parameters get smaller.
This is most evident for the higher order polynomial features. But Alpha must be selected carefully. If alpha is too large, the coefficients will approach zero and underfit the data. If alpha is zero, the overfitting is evident.

In order to select alpha, we use cross validation.
To make a prediction using ridge regression, import ridge from sklearn.linear_models. Create a ridge object using the constructor. The parameter alpha is one of the arguments of the constructor.
We train the model using the fit method. To make a prediction, we use the predict method. In order to determine the parameter alpha, we use some data for training. We use a second set called validation data. This is similar to test data, but it is used to select parameters like alpha. We start with a small value of alpha. We train the model, make a prediction using the validation data, then calculate the R-squared and store the values. Repeat the value for a larger value of alpha.

We select the value of alpha that maximizes the R-squared. Note that we can use other metrics to select the value of alpha, like mean squared error.

## 5.5 Grid Search
Grid Search allows us to scan through multiple free parameters with few lines of code.

Parameters like the alpha term discussed in
the previous video are not part of the fitting or training process. These values are called hyperparameters.

Scikit-learn has a means of automatically
iterating over these hyperparameters using cross-validation. This method is called Grid Search.

Grid Search takes the model or objects you would like to train and different values of the hyperparameters. It then calculates the mean square error or R-squared for various hyperparameter values,
allowing you to choose the best values.

We start off with one value for hyperparameters and train the model. We use different hyperparameters to train the model. We continue the process until we have exhausted the different free parameter values. Each model produces an error.
We select the hyperparameter that minimizes the error.

To select the hyperparameter, we split our dataset into three parts, the training set, validation set, and test set. We train the model for different hyperparameters. We use the R-squared or mean square error for each model. We select the hyperparameter that minimizes the mean squared
error or maximizes the R-squared on the validation set. We finally test our model performance using the test data.

## 5.6 Module 5 Lesson Summary
- Identify over-fitting and under-fitting in a predictive model: Overfitting occurs when a function is too closely fit to the training data points and captures the noise of the data. Underfitting refers to a model that can't model the training data or capture the trend of the data.
- Apply Ridge Regression to linear regression models: Ridge regression is a regression that is employed in a Multiple regression model when Multicollinearity occurs.
- Tune hyper-parameters of an estimator using Grid search: Grid search is a time-efficient tuning technique that exhaustively computes the optimum values of hyperparameters performed on specific parameter values of estimators.
