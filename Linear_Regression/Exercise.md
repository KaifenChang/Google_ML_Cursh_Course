> #### Learning objectives
> - read a .csv file into a pandas DataFrame
> - Explore a dataset with Pyrhon visualization libraries
> - Experiment with different features to build a linear regression model
> - compare training runs using root mean squared error and loss curves

***
# Part 1- Setup Exercise

#### 1. Load dependencies 
```python
# genereal
import io # for handling input/ output operations

# data
import numpy as np
import pandas as pd

# machine learning
import keras

# Data visualiztion
import plotly.express as px
from plotly.subplots import make_subplots
import plotly.graph_objects as go
import seaborn as sns
```

#### 2. Load the dataset and update the dataframe
```python
# load the dataset
chicago_taxi_dataset = pd.read_csv("https://download.mlcc.google.com/mledu-datasets/chicago_taxi_train.csv")

# read the dataset
## updates the datafrae to use specific columns
training_df = chicago_taxi_dataset[['TRIP_MILES', 'TRIP_SECONDS', 'FARE', 'COMPANY', 'PAYMENT_TYPE', 'TIP_RATE']]

print('Read dataset completed successfully.')
print('Total number of rows: {0}\n\n'.format(len(training_df.index)))
training_df.head(200)
```

> #### Notes
> 1. Dependencies: external libraries
> 
> 2. Pandas note
> 2.1 updated the dataframe with spe. cols: `updated_dataframe = dataframe[["feature_columns"]]`
> 2.2 `.index`: number assigned to each example (row) 
> `len(df.index)`: gives the total numbers of examples
> 2.3 `dataframe.head(num)`: get the first num rows
> 3. `{k}.format(get a num k)`: take the num k into {}

> #### Procedure: Setting up
> 1. import dependencies
> 2. load the dataset
> 3. update the dataframe :only take the usedful features
> 
***
# Part 2 - Dataset Exploration
#### 1. View data statisitc
- meed to know the data
- use `DataFrame.describe`
```python
print('Total number of rows: {0}\n\n'.format(len(training_df.index)))
training_df.describe(include='all')
```
| Q|A | |
|-|-| -|
What is the max fare?|159.25 $ | `maxfare = training_df['FARE'].max()`
What is the mean distance across all trips?| 8.289463 miles |`mean_distance = training_df['TRIP_MILES'].mean`
How many cab companies are in the dataset? | *31* | `unique_companies =  training_df['COMPANY'].nunique()`
What is the most frequens payment type?| Credit card |`most_freq_payment_type = training_df['PAYMENT_TYPE'].value_counts().idxmax()`
Are any features missing data?| No | `missing_values = training_df.isnull().sum().sum()`

#### 2. Generate a correlation matrix
> Determine whether features correlated with the label

| Value|Description|
| -| -|
|**1.0**| perfect positive correlation
|**-1.0**|perfect negetive correlation
|**0.0**| no correlation
##### View correlation matrix
```python
training_df.corr(numeric_only = True)
```

| Q | A|
|- | -
|Which feature correlates **most strongly** to the label FARE?| TRIP_MILES
|Which feature correlates **least strongly** to the label FARE?|TIP_RATE

#### 3. Visualize relationships in dataset
##### View pair plot
```python
sns.pairplot(training_df, x_vars=["FARE". "TRIP_MILES", "TRIP_SECONDS"], v_vars=["FARE". "TRIP_MILES", "TRIP_SECONDS"])
```

> #### Notes
> 1. `.idxmax()`: retrun the index of the first occurance of the maximum value
> 2. correlation: -1.0 ~ 0.0 ~ 1.0, 
>   use `dataframe.corr()` to check
> 3. `sns.pairplot(data, vars = [""])` is from libeary `seaborn`
>   useful for visualizing relationship

> #### Procedure: Dataset exploration
> 1. view the statistics
> 2. generate the correlation matrix (`df.corr()`)
> 3. visualize the relationships (`sns.pairplot(df)`)
***
# Part 3 - Train Model
#### 1. Define functions to view model information
generating 2 plots
1. **a scatter plot**: 
   1. feature v.s.the label 
   2. with a line indicaate the output of the trained model
2. **a loss curve**
these are for visualizing the results after each experiment

**Plotting functions**
```python
def make_plots(df, feature_names, label_name, model_output, sample_size=200)
    random_sample = df.sample(n=sample_size).copy()
    random_sample.reset_index()
    weights, bias, epochs, rmse = model_output

    is_2d_plot = len(feature_names) == 1
    model_plot_type = "scatter" if is_2d_plot else "surface"
    fig = make_subplots(row=1, cols=2,
                        subplot_titiles=("Loss Curve", "Model Plot"),
                        specs=[[{"type": "scatter"},{"type": model_plot_type}]]
    plot_data(random_sample, feature_names, label_name, fig)
    plot_model(random_sample, featyre_names, weight, bias, fig)
    plot_loss_curve(epochs, rmse, fig)

    fig,show
    return
```
and a rest can be learnt latter

#### 2. Define ML functions
```python
def build_model(my_learning_rate, num_features):
    """Create and compile a simple linear regression model."""
    input - keras.INput(shape=(num_features))
```

#### 3.1 Train a model with one feature

##### Experiment 1
##### Experiment 2

#### 3.2 Train a model with two features
##### Experiment 3
***
# Part 4 - Validate Model