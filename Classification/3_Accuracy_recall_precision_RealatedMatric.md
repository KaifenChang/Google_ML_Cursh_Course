# Classification: Accurancy, recall, precision, and related metrics 
### Accuracy
$\text{Accuracy} = \frac{\text{correct classification}}{\text{total classification}} = \frac{\text{TP + TN}}{\text{TP + TN + FP + FN}}$

would like the FP and FN be 0
then the accuracy would be 1.0 (100%)

#### Recall (True Positive Rate)
The porpotion of all actual positives that were classified as positive

$\text{Recall (TPR)} = \frac{\text{correctly classified actual positives}}{\text{all actual positives}} = \frac{\text{TP}}{\text{TP + FN}}$

**FN** is False negative => 0 & 0 = 1

#### False Positive Rate(FPR)
The porpotion of all actual negatives that were classified as incorrectly positive
aka **probability of false alarm**

$\text{FPR} = \frac{\text{incorrectly classified actual negatives}}{\text{all actual negatives}} = \frac{\text{FP}}{\text{TN + FP}}$

#### Precision

$\text{FPR} = \frac{\text{correctly classified actual positives}}{\text{everything classified as positive}} = \frac{\text{TP}}{\text{TP + FP}}$
