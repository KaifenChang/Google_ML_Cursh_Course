# Classification: Prediction Bias  

### Overview  
>Prediction bias is a quick diagnostic check that helps identify potential issues with a model or its training data. 

It measures the difference between
-  the **mean of a model's predictions** and 
-  the **mean of ground-truth labels** in the dataset.  

### Definition  
- **Prediction Bias** = Mean of model predictions - Mean of ground-truth labels  
- A model trained on a dataset where **5% of emails are spam** should predict, 
  - on average, that **5% of classified emails are spam**.  
- If the mean of predictions matches the mean of the ground-truth labels, 
  - => the model has **zero prediction bias** (though it may still have other issues).  

### Example  
- **Ideal case**:  
  - Ground-truth spam percentage: **0.05 (5%)**  
  - Model's average predicted spam probability: **0.05 (5%)**  
  - --> Zero prediction bias**  

- **Biased case**:  
  - If the model predicts that **50% of emails** are spam instead of **5%**, then there is a significant prediction bias.  
  - This suggests issues with either:  
    - The **training dataset**  
    - The **new dataset** the model is applied to  
    - The **model itself**  

### Causes of Prediction Bias  
1. **Biases or noise in the data**  
   - Biased sampling in the training dataset  
   - Incomplete or unrepresentative data  

2. **Over-regularization**  
   - Too-strong regularization can **oversimplify the model**, 
     - ==> causing it to lose necessary complexity  

3. **Bugs in the training pipeline**  
   - Errors in data processing, 
   - feature engineering
   - training code can introduce biases

4. **Insufficient features**  
   - The set of input features may be **inadequate** for the classification task, 
   - limiting the model’s ability to learn correct patterns
