# Linear Regression

> Learning objectives
> - Explain a loss function and how it works
> - Define and describe how gradient descent finds the optimnal model parameters
> - Describe how to tune hyperparameters to efficiently train a model

***
# 1. Intro

## Linear regression
- statistical technique 
- relationship between **features** and a **label**

### Example 1: 
**Goal**: predict a car's fuel efficiency 
**Features**: Weight?(pound), Acceleration, Year,... etc
**Label**: Miles/gallon

***Model***: Drawing a bset fit line
![f_2](https://developers.google.com/static/machine-learning/crash-course/linear-regression/images/car-data-points-with-model.png)

## Linear regression equation
$y = mx + b$
  - $y$ the value want to predict
  - $m$ the slope
  - $x$ input value
  - $b$ y-intercept

***In ML (Single feature)***
> $y' = b +w_1x_1$
  - $y$ the predicted lable (the output)
  - $b$ the **bias** of the model
    - also y(lable)-int, or so called $w_0$
    - is a *parameter* of the model
    - calculated during training
  - $w_1$ the **weight** of the feature
    - same concept as the *slope*
    - is a *parameter* of the model
    - calculated during training
  - $x_1$ a **feature** -the input

![math](https://developers.google.com/static/machine-learning/crash-course/linear-regression/images/equation.png)

***In ML (Multiple features)***
> $y' = b + w_1x_1 + w_2x_2 + w_3x_3 + w_4x_4$
> - $y'$ is the predicted label—the output
- for this formula
  - 4 features
  - could get 4 plots with different x-axis(feature)

***
## Summmary
> 1. The linear regression equation:
> $y' = b + w_1x_1 + w_2x_2 + w_3x_3 + w_4x_4$ + ...
>   $y'$: predicted label
>   $b$: bias (parameter)
>   $w$: weight (parameter)
>   $x$: feature
> 2. The bias and weight would updated during training

