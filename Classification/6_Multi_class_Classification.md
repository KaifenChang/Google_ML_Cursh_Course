# Classification: Multi-class Classification  
>Multi-class classification is an **extension of binary classification** for problems involving **more than two classes**.  

### Handling Multi-class Classification as Binary Classification  
- If **each example belongs to only one class**, 
  - the multi-class problem can be decomposed into multiple **binary classification problems**.  
- One class is treated as 
  - the "positive" class
  - all other classes are combined into a "negative" class.  
- This process is repeated for each original class.  

### Example  
- **Three-class problem (A, B, C)**:  
  - **Step 1**: Train a binary classifier to distinguish between **(A+B) vs. C**.  
  - **Step 2**: Train another binary classifier to separate **A vs. B** within the (A+B) group.  
  - By following this approach, we achieve multi-class classification using multiple binary classifiers.  

- **Real-world application**:  
  - **Handwritten digit recognition**: A model takes an image of a handwritten digit and classifies it as one of **0-9**.  

### Multi-label Classification  
- If an example can **belong to multiple classes at the same time**, the problem is known as **multi-label classification**.  
- Unlike **multi-class classification**, multi-label classification allows a single example to have **multiple labels**.  
