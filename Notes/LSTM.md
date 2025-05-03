# Understanding `return_sequences` in LSTM (Keras/TensorFlow)

The `return_sequences` parameter in `LSTM` (or any RNN layer) controls whether the layer outputs **all hidden states** for each timestep or just the **last hidden state**. Below is a detailed breakdown.

---

## **1. `return_sequences=False` (Default)**
### **Behavior**
- Returns **only the last hidden state** (at the final timestep).  
- **Output Shape**: `(batch_size, units)`  

### **Use Case**
- **Sequence-to-One** tasks (e.g., classification, regression).  
- When the next layer (e.g., `Dense`) expects a single vector.

### **Code Example**
```python
from tensorflow.keras.layers import LSTM

model.add(LSTM(units=64))  # Returns only the last output
```

### Illustration
Input Sequence:  [t1, t2, t3]

LSTM Output: [h3] <br># Only last state

## **2. `return_sequences=True`**
### **Behavior**
- Returns all hidden states (one per timestep).
- Output Shape: `(batch_size, timesteps, units)`

### **Use Case**
- Stacked LSTMs (next LSTM needs sequences).
- Sequence-to-Sequence tasks (e.g., machine translation, time-series forecasting).

### **Code Example**
```python
model.add(LSTM(units=64, return_sequences=True))  # Returns all outputs
```
### Illustration
Input Sequence:  [t1, t2, t3]

                 |    |    |
LSTM Output:     [h1, h2, h3]  <br># All states
<br><br>
## Key Scenarios

| Scenario                         | `return_sequences` | Output Shape                     | Typical Use Case             |
|----------------------------------|--------------------|----------------------------------|------------------------------|
| Single LSTM → Dense Layer        | `False` (default)  | `(batch_size, units)`            | Classification/Regression    |
| Stacked LSTMs                    | `True` (1st LSTM)  | `(batch_size, timesteps, units)` | Deep RNNs                    |
| Sequence-to-Sequence (e.g., NMT) | `True`             | `(batch_size, timesteps, units)` | Time-series, text generation |

## Example: Stacked LSTMs
```python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import LSTM, Dense

model = Sequential([
    # First LSTM: Returns sequences for the next LSTM
    LSTM(64, return_sequences=True, input_shape=(10, 32)),  # (timesteps=10, features=32)
    # Second LSTM: Returns only the last output
    LSTM(64),
    # Dense layer for prediction
    Dense(1)
])
```
<br><br>
## When to Avoid `return_sequences=True`?
- If the next layer (e.g., Dense) expects a single vector.
- For single-step predictions (e.g., binary classification).
<br><br>

## Summary
- Use `return_sequences=True` for:
  - Stacked LSTMs.
  - Sequence-to-sequence tasks.
- Use `return_sequences=False` for:
  - Final LSTM in a stack.
  - Sequence-to-one tasks.