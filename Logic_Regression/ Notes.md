# Logistic Regression:
> Learning Objectives
> - identify use cases for performing logistic regression
> - explain how logiestic regression models use the sigmoid function to calculate probability
> - explain why logistic regression use log loss instead of squared loss
> - explain the importance of tegularization when training logistic regression models

Logistic Regression
- e.g. spam email ditection
- use 1: soam
- use 0: not spam
- 0.627? likelihood of spam
- -> predicted the probability
  
- use the functions and only observe the range of [0, 1]
- see if the curve converge to 0 or 1

- Good idea for predicting between 2 possible outcome

***
## Logistic Regression: Calculating a probability with the sigmoid function

Logistic regression is an efficient mechanism for calculating **probability**
e.g.
The spam-prediction model takes an email as input, and putput a value of `0.92`
--> This implies `93.2%` probability that the email is spam

Coverted to a **bianry category**
- True or False
- Spam or not Spam

### Sigmoid function 
$f(x)=\frac{1}{1+e^{-x}}$
![sigmoid](https://developers.google.com/static/machine-learning/crash-course/logistic-regression/images/sigmoid_function_with_axes.png)
- where converge to 1 or 0

#### Transforming a linear output using the sigmoid function
The linear component of a regression model:
$ z = b + w_1x_1 + w_2x_2 + ... + w_Nx_N $
- `z` is the output, also called **log odd**
- `b` is the bias
- `w` are the model's learned weights
- `x` are the deature values for a particu;ar example

Transfering the linear ouput into the logistic regressiion output
$ y' = \frac{1}{1+e^{-z}}$
- `y'` is the output of the logistic tegression model
- `z` is the linear output (calculated in the preceding equation)

*** 
## Logistic Regression: Loss and regularization
Logistic regression use the same traning model as linear regression, but 2 difference
- Logistic regression use **Log Loss** as loss function
- applying **regularization** to prevent overfitting

### Log Loss
Squared loss 
- used in linear regression
- the rate of change of the output values is constant

Log Loss
- for the rate of change is not constant
  - since the sigmoid curve is s-shape
$\text{Log Loss} = \sum_{(x,y) \in D} -y \log(y') - (1 - y) \log(1 - y')$
- return the log of the magnitute of change
- $(x,y) \in D$ is the datasetcontaining many labeled examples, which are $(x, y)$ pairs
- $y$ is the labeled example
  - Logistic regression
  - y must either be 0 or 1
- $y'$ is the prediction
  - stands between 0 and 1
  - given the set of features in $x$

#### Regularization
**penalize complexity**
- adding constraints or modification 
- prefventing to be too complex and overfitting
- without regularizationL the loss will approach to 0 where is too confident => overfitting
- 2 strategies to decrease model complexity
  - L2 regularization
  - Early stopping

***
> ## Logistic Regression Summary
> - use when there are 2 outcomes
> - use sigmoid functiion (s-shape) for the range in (0, 1)
>   - `y` would be either 0 or 1
>   - `y'` would be located between 0 or 1 
> - log loss: for the rate of change is not in constant
> - use regularization to prevent overfitting
