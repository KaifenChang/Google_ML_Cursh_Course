## Thresholds and the confusion matrix
#### Spam email example
The logistic regression model predicts a value between 0 and 1, which is the probability of the given email is spam
- a prediction of 0.5 => 50% likelihood that this email is spam
- choose the threshold probability (**classification threshold**) to convert the raw numerical output (e.g. `0.75`) into two categories
  - spam: **positive class**
  - not spam: **negative class**
- suppose there are two email scoring 0.99 and 0.51
  - if set the classification threshold to 0.5
  - both emails are classified as spam

### Confusion matrix
> 4 possible outcomes

use table or so call matrix to present
|                        | Actual positive         | Actual negative         |
| ---------------------- | ----------------------- | ----------------------- |
| **Predicted positive** | **True positive (TP)**  | **False positive (FP)** |
| **Predicted negative** | **False negative (FN)** | **True negative (TN)**  |

#### e.g. spam email
|                        | Actual positive         | Actual negative         |
| ---------------------- | ----------------------- | ----------------------- |
| **Predicted positive** | **True positive (TP)** : A *spam email* correctly classified as a spam email | **False positive (FP)**: A *not-spam email* misclassified as spam. |
| **Predicted negative** | **False negative (FN)**: A *spam email* misclassified as not-spam.  | **True negative (TN)**:A *not-spam email* correctly classified as not-spam.  |

when the total of actual positives is not close to the total of actual negative
--> the dataset is **imbalanced**

#### Types
1. Separated: most positive examples have higher scores than negative examples
2. Unsepareted: positive examples have lower scores than negative examples
3. Imbalanced: containing only a few examples of the positive class