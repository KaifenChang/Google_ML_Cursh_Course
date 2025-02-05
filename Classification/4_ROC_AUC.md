# Classification: ROC and AUC

### Receiver-operating characteristic curve (ROC)
> A visual representation of a classifier’s performance across all classification thresholds.

#### Plot Construction:
-  Created by plotting the true positive rate (TPR) against the false positive rate (FPR) for various threshold settings.
- thresholds are often sampled or based on the distinct prediction scores of the model.

#### Perfect Model:
- A perfect model achieves
  - TPR = 1.0 and FPR = 0.0 at some threshold.
- In ROC space, this point would appear at (0,1). 
- If we consider other thresholds, the model’s ROC curve would connect (0,0) → (0,1) → (1,1) 
  - forming a “L-shaped” path (an idealized performance boundary).

![ROC](https://developers.google.com/static/machine-learning/crash-course/images/auc_1-0.png)

#### Constructing the ROC curve
To construct an ROC curve, you would typically follow these steps:

1. **Train a classification model**: This could be any model like logistic regression, support vector machine, or a decision tree.
2. **Predict probabilities**: Use the trained model to predict the probability of each instance belonging to the positive class.
3. **Vary the classification threshold**: Start with a threshold of 0 and gradually increase it to 1. For each threshold, classify instances with a predicted probability greater than the threshold as positive and the rest as negative.
4. **Calculate TPR and FPR**: At each threshold, calculate the TPR and FPR based on the model's predictions.   
5. **Plot the ROC curve**: Plot the TPR on the y-axis and FPR on the x-axis. The resulting curve illustrates the trade-off between TPR and FPR at different thresholds.   

### Area under the curve (AUC)
> The area under the ROC curve (AUC) 
> - measures the probability that a randomly chosen positive example is ranked higher than a randomly chosen negative example.


#### Perfect Model (AUC = 1.0)
  - Forms a square with sides of length 1
    - leading to an AUC of 1.0.  
  - The model always correctly ranks a positive instance higher than a negative instance.  
  - e.g.
    - A spam classifier with AUC = 1.0 always assigns a higher probability to a spam email than to a legitimate email.  

#### Random Guessing Model (AUC = 0.5):  
  - The ROC curve follows a **diagonal line from (0,0) to (1,1)**.  
  - Represents a classifier that performs no better than random chance.  
  - e.g.
    -  A spam classifier with AUC = 0.5 assigns a higher probability to a spam email 
       -  than a legitimate one only **half the time** (equivalent to flipping a coin).  

#### Implications of AUC Values:
  - **AUC > 0.5**: Model performs better than random guessing.  
  - **AUC < 0.5**: Model is worse than random guessing (it systematically misclassifies examples).
![AUC](https://developers.google.com/static/machine-learning/crash-course/images/auc_0-5.png)


***

## Key Reasons for ROC and AUC Significance

- **Model Comparison**  
  - AUC provides a single, comparable metric for evaluating the performance of different models.  
  - A higher AUC generally indicates better discriminatory power.  

- **Threshold Selection**  
  - The ROC curve helps visualize the trade-off between **true positive rate (TPR)** and **false positive rate (FPR)** at different thresholds.  
  - This aids in selecting the optimal threshold based on the specific needs of the application.  

- **Handling Imbalanced Datasets**  
  - ROC and AUC are **less sensitive to class imbalance** compared to metrics like accuracy.  
  - They evaluate the model’s ability to **rank instances correctly** rather than just measuring overall correctness.  
  - Accuracy can be misleading in imbalanced datasets, as a model might achieve **high accuracy by predicting the majority class** most of the time.  

- **Alternative Metrics for Imbalanced Data**  
  - In cases of class imbalance, **F1-score** (which considers both precision and recall) can be a more informative metric than accuracy.  

- **Robustness to Class Distribution Drift**  
  - ROC AUC is more **tolerant to changes in class distribution**, which is common in real-world applications where the proportion of positive and negative cases may shift over time.
