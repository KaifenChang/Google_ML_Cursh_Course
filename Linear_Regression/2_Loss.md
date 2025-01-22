# Linear Regression: Loss
***
### Loss
- a numerical metric 
  - how wrong the models's predictions are
- the distance between the prediction and the actual labels
  -  $distance = \text{actual value} - \text{predicted value}$
  -  actual value: original plot
  -  predicted value: the best fit line here
    - need to remove the sign
      1. taking absolute value: $|Distance|$
      2. square it: $(Distance)^2$
- goal: min the loss

![](https://developers.google.com/static/machine-learning/crash-course/linear-regression/images/loss-lines.png)

### Type of loss

| Loss type | Definition                 |Equation |
|-----------|----------------------      | ----------------------| 
|$L_1$ loss |sum of abs                            |$\sum \lvert \text{actual value} - \text{predicted value} \rvert$
|(MAE) Mean absolute error |average of L1|$\frac{1}{N}\sum \lvert \text{actual value} - \text{predicted value} \rvert$
|$L_2$ loss |sum of square                             |$\sum (\text{actual value} - \text{predicted value} )^2$
|(MSE) Mean squared error |average of L2|$\frac{1}{N}\sum (\text{actual value} - \text{predicted value} )^2$

**outlier (異常值)**: the data point which out of the range

**MAE v.s. MSE**
|  | Outliers|Other data points|||
|---| ---| ---| ---|---|
| MAE | further | **closer** |更穩定|對異常值敏感性低，對普通數據的預測準確性較高|
| MSE  | **closer** | further | 更分散|更注重大誤差點

***
### Summary
> 1. Loss is the value of **inaccurency**
> 2. Want to minimized
> 3. MAE is more stable 
> 4. MSE could zoom out the error 