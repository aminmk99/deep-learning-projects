# Regularization in Machine Learning  

## What is Regularization?  
Regularization is a technique used in machine learning to prevent **overfitting** by adding a penalty to the loss function. Overfitting occurs when a model learns the noise in the training data instead of the underlying pattern, leading to poor generalization on new data.

## Why is Regularization Important?  
- Prevents overfitting by discouraging complex models.
- Improves model generalization to unseen data.
- Helps in dealing with multicollinearity (in linear regression).

## Types of Regularization  
### 1. L1 Regularization (Lasso Regression)  
- Adds the **absolute** value of coefficients (`|w|`) as a penalty term.  
- Encourages sparsity by forcing some coefficients to become zero (feature selection).  
- Cost function:  
  \[
  J(w) = Loss + \lambda \sum |w_i|
  \]

### 2. L2 Regularization (Ridge Regression)  
- Adds the **squared** value of coefficients (`w²`) as a penalty.  
- Shrinks coefficients towards zero but does not make them exactly zero.  
- Cost function:  
  \[
  J(w) = Loss + \lambda \sum w_i^2
  \]

### 3. Elastic Net  
- A combination of L1 and L2 regularization.  
- Useful when there are correlated features.  
- Cost function:  
  \[
  J(w) = Loss + \lambda_1 \sum |w_i| + \lambda_2 \sum w_i^2
  \]

## Regularization in Neural Networks  
Regularization in deep learning is achieved using:
- **L1/L2 weight penalties** (applied to network weights).
- **Dropout** (randomly disabling neurons to prevent co-adaptation).
- **Batch Normalization** (normalizing activations to stabilize learning).
- **Early Stopping** (stopping training when validation loss stops improving).

## Code Example (L2 Regularization in TensorFlow/Keras)
```python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense
from tensorflow.keras.regularizers import l2

model = Sequential([
    Dense(64, activation='relu', kernel_regularizer=l2(0.01), input_shape=(10,)),
    Dense(1, activation='sigmoid')
])
