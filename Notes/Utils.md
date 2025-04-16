### 🔢 How to Get the Number of Unique Classes in a Dataset (Using NumPy)

When working with labeled datasets, it's often useful to inspect the label distribution — for example, to find out **how many distinct classes** are present in your data.

Here’s how to do it using `numpy`:

---

#### ✅ Get the Unique Class Labels

```python
import numpy as np

unique_labels = np.unique(y_train)
print("Unique class labels:", unique_labels)
```
---
<br><br>

## 🔍 How to Check If We're Using a GPU in TensorFlow

When working with deep learning, it's often important to check if our code is running on a **GPU** or falling back to the **CPU**.

Here's how we can do it using **TensorFlow**:

---

### ✅ Check Available Devices

```python
import tensorflow as tf

# List physical devices
tf.config.list_physical_devices()
```
This returns a list of available devices like CPUs or GPUs.

### 🧠 Check Specifically for GPU
```python
import tensorflow as tf

# Check if a GPU is available
gpus = tf.config.list_physical_devices('GPU')

if gpus:
    print("✅ GPU is available!")
else:
    print("⚠️ GPU is NOT available, using CPU.")
```
We can also print the actual device name like this:
````python
from tensorflow.python.client import device_lib
print(device_lib.list_local_devices())
````

