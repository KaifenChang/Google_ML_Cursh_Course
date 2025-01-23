# Linear regression: Hyperparameters

**Hyperparameters**: we can control
- Learning rate
- Batch size
- Epochs

**Parameters**: from the model itself
- weights
- bias
***

### Learning rate
#### Concept
- a floating number point
- influences how quickly the model converges
- if too low
  - take long time to converge
- if too high
  - never converge, keeps finding lowest loss
- **Goal**: pick a ideal learning rate that the model **converges** quickly
  - once converge: get the weight and bias with min loss

#### Action
- determine the magnitude of the changes to make to the weight and bias during each step of the gradient decent process
- $\text{learning rate} \times \text{gradient}$ => New model parameter (bias and weight)
- The gradient is essentially the **slope** of the current parameters
- so the parameters has the propotion based on the slope
  - if the slope is big: large step -> more adjustment on the model
  - if the slope is small: small step -> less adjustment on the model

### Batch size
#### Concept
- refers to the number of examples that the model processes before updating its weight and bias
- not prqctical using the full batch

#### Techniques for 
**Stochastic gradient descent(SGD)**
- only a single example (batch size of one) per iterarion
- its noisy (more variation increases)
- *updates weights and bias after each individual example*


**Mini-batch stochastic gradient descent (mini-batch SGD)**
- batch size: >1 and <N
- get the average of the gradient
- *updates weights and bias after a subset (batch) of examples*
  
### Epochs
$\text{1 epoch} = \frac{N}{\text{batch size}} = \text{iterations}$
- an epoch = how the model processed through every example in the training set once

Example
- 1000 examples (N)
- mini-batch size of 100 examples 
  => 10 iterations to complete 1 **epoch**
  =>$\frac{1000}{\text{100}} = \text{10 iterations} = \text{1 epoch} $

![epoch](https://developers.google.com/static/machine-learning/crash-course/linear-regression/images/batch-size.png)

| Batch type    | E.g. | Updated the weight and bias|
|-----------    |--                                 |--|
| Full Batch    |1000 examples <br> 20 epochs <br>  |20 times, updated after each epoch|
| SGD           |1000 examples <br> 20 epochs <br>  |20000 times |
| mini-batch SGD|1000 examples <br> batch size = 100 <br>20 epochs <br> |200 times|

***
#### Summary
> Learning rate
> - the size of the steps for the model to take during gardient descent
> - pick a ideal learning rate that the model **converges** quickly
> 
> Batches: number of examples processes before 
> Epochs: One complete pass through the entire dataset.
>| Batch Type    | Processes                      | Updated the Weight and Bias                    |
>| ------------------ | ---------------------------------- | -------------------------------------------------- |
>| Full Batch     | All examples in one go             | Once per epoch                                     |
>| SGD         | One example at a time              | $ \text{Total updates} = \text{examples} \times \text{epochs}$  |
>| Mini-batch SGD | A subset of examples per iteration | $ \text{Total updates} = \left( \frac{\text{examples}}{\text{batch size}} \right) \times \text{epochs}$|
