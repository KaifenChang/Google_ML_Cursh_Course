# Linear regression: Gradient descent, Hyperparameter
***
### Gradient descent
- a math technique
- find the lowest loss by modifing the bias and weight repeatly

#### Steps
1. Calculate the loss with the current weight and bias.
2. Determine the direction to move the weights and bias that reduce loss.
3. Move the weight and bias values a *small amount* in the direction that reduces loss.
4. Return to step one and repeat the process until the model can't reduce the loss any further.

### Model convergence and loss curves
**Loss curve**
- how the loss changes as the model trains
![loss_curve](https://developers.google.com/static/machine-learning/crash-course/linear-regression/images/convergence.png)
- converges after 1000 iterations

### Convergence and conves functions
loss function will produce a **convex** surface
![surface](https://developers.google.com/static/machine-learning/crash-course/linear-regression/images/convexity.png)
  - x-axis: wight
  - y-axis: bias
  - z-axis: loss

- converge since the weight and bias has the slope approx. to 0
- won't find exact min value

***
### Summary
> 1. Gradient descent is an iterative process that finds the best weights and bias that minimize the loss.
>   - a process making the parameters converge to the values that min the loss
> 2. The loss function would find the surface
> 3. From the surface, we want the min point (slope ~ 0)
