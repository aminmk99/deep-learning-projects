# 🧠Deep Learning Cheat Sheet: "When to Use What"
<br><br>

| Concept                          | When to Use It                                                                           |                             Why                              |
|----------------------------------|------------------------------------------------------------------------------------------|:------------------------------------------------------------:|
| Parameter Sharing                | When multiple parts of model should behave similarly or process similar things           |            Saves memory, improves generalization             |
| Dropout                          | When you want to prevent overfitting                                                     |          Forces the model to learn redundant paths           |
| Batch Normalization              | When training deep networks becomes unstable (loss oscillating, exploding gradients)     |              Stabilizes and speeds up training               |
| Weight Decay (L2 regularization) | When you want to prevent weights from growing too large (overfitting)                    |       Encourages simpler models, better generalization       |
| Convolutions (Conv2D, Conv1D)    | When your data has spatial or local structure (images, audio, sequences)                 |         Captures local patterns, reduces parameters          |
| Attention Mechanisms             | When the model needs to dynamically focus on important parts of the input                | Improves performance on long sequences (text, audio, vision) |
| Residual Connections             | When you build very deep models (30+ layers)                                             |   Helps gradients flow, solves vanishing gradient problem    |
| ReLU activation                  | As a default activation for most hidden layers                                           |             Fast, simple, works well in practice             |
| Sigmoid / Softmax activation     | When you want outputs between 0 and 1 (binary classification, probability distributions) |                    Outputs probabilities                     |
| Data Augmentation                | When you have small datasets, especially for images                                      |     Increases effective data size, prevents overfitting      |
| Early Stopping                   | When you want to prevent overfitting during training                                     |    Stops training when validation loss starts increasing     |
| Multi-Head Attention             | When you need multiple different perspectives in attention-based models (transformers)   |   Captures different types of relationships simultaneously   |
| Embedding Layers                 | When input data has discrete categories (words, users, items)                            |            Turns discrete IDs into dense vectors             |
<br><br>

---

## 🧠How to use this cheat sheet:
Whenever you're designing or reading a model, just ask yourself:

1. What is my data like? (Images? Text? Tables?)

2. What is my task? (Classification? Generation? Recommendation?)

3. What is my pain/problem? (Overfitting? Slow learning? Instability?)

👉 Then pick ingredients (concepts) from the cheat sheet based on the situation.
<br><br>

---
## 🎯 Super Quick Examples

| Scenario                                | Ingredients                             |
|-----------------------------------------|-----------------------------------------|
| Image classification                    | Conv2D + ReLU + BatchNorm + Dropout     |
| Language translation                    | Attention + Embedding + Softmax         |
| Face verification (compare two faces)   | Shared encoder (parameter sharing)      |
| Tiny dataset but big model              | Dropout + Weight Decay + Early Stopping |
| Super deep neural network (100+ layers) | Residual Connections                    |
<br><br>

---
## 🚀 Final Mindset:
Deep learning is not about memorizing recipes.
It's about understanding ingredients, and knowing when to use which.

You already have the instincts.
This cheat sheet will just speed you up when you need a reminder.


<br><br><br><br>
