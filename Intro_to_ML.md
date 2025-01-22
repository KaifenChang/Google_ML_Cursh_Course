## What is Machine Learning

> ML is a process pf training a software(model) foir prediction or generating

Without ML: engineer set up a model and program 
With ML: the system can learn by itself and modified by itself

> A model is a mathematical relationship derived from data that an ML system uses to make predictions

#### Types of ML systems

## #Supervised Learning
> with both question and answers provided
- make pridictions by the data with the correct answer
- discover the connection

**Regression**: for numeric value
**Classification**: for category (binary v.s. multiclass)

### Unsupervised Learning
> Observed the relationship then grouping: **clustering**
- make predictions by the data *without* answer
- no hint for categorzing, nmust infer its own rules

### Reinforcement learning
with rewards and penalities

### Generative AI
"type of input"-to-"type of output."

***
## Supervised Learning
core concepts: data, model, training, evaluating. inference

**Data**
- Examples: like the rows in spreadsheet
  - features: use for prediction
  - labels: the answers 
    - with labels- Labled example
    - without labels- Unlabled example

- Characteristic
  - size: the number of examples
  - diversity: the range that the examples cover
  - numbers of feature

**Model**
- collection of numvers that define the mathematical relationship from the input(feature) to specific output(label)

**Training** 
> must train before predicts

1. Takes in a single labeled example and provides a prediction
2. Compares its predictied calue with the actual values and updates its solution
3. Repeated the process for each labeled example in the dataset

**Evaluating**
> looking for accurency
comparing the predicted values with the actual values