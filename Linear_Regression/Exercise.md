> #### Learning objectives
> - read a .csv file into a pandas DataFrame
> - Explore a dataset with Pyrhon visualization libraries
> - Experiment with different features to build a linear regression model
> - compare training runs using root mean squared error and loss curves

***
# Part 1- Setup Exercise
***
#### Load dependencies 
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

#### Load the dataset and update the dataframe
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
>
***
# Part 2 - Dataset Exploration
***
#### View data statisitc
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

#### Generate a correlation matrix
> Determine whether features correlated with the label

| Value|Description|
| -| -|
|**1.0**| perfect positive correlation
|**-1.0**|perfect negetive correlation
|**0.0**| no correlation
```python
training_df.corr(numeric_only = True)
```

| Q | A|
|- | -
|Which feature correlates **most strongly** to the label FARE?| TRIP_MILES
|Which feature correlates **least strongly** to the label FARE?|TIP_RATE

#### Visualize relationships in dataset

> #### Notes
> 1. `.idxmax()`: 
> 2. 
***
# Part 3 - Train Model

***
# Part 4 - Validate Model