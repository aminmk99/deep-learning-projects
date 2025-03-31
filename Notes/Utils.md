### 🔢 How to Get the Number of Unique Classes in a Dataset (Using NumPy)

When working with labeled datasets, it's often useful to inspect the label distribution — for example, to find out **how many distinct classes** are present in your data.

Here’s how to do it using `numpy`:

---

#### ✅ Get the Unique Class Labels

```python
import numpy as np

unique_labels = np.unique(y_train)
print("Unique class labels:", unique_labels)
