# 🧠 Horse vs Human Classification — CNN vs MobileNetV2

This notebook explores a binary image classification task (Horse 🐴 vs Human 🧍‍♂️) using two different approaches:

1. **Custom CNN built from scratch**
2. **Transfer learning with MobileNetV2 (pretrained on ImageNet)**

---

## 🗂️ Contents

- 🔍 Data loading and preprocessing with `ImageDataGenerator`
- 🧱 Custom CNN architecture using `Sequential` API
- 🧠 MobileNetV2-based model using both `Sequential` and `Functional` APIs
- 📊 Accuracy & loss comparison (training vs validation)
- 💡 Key insights on transfer learning benefits

---

## 🚀 Technologies Used

- Python + TensorFlow / Keras
- Jupyter Notebook
- MobileNetV2 (with weights from ImageNet)
- Matplotlib (for visualization)

---

## 📈 Results

- Custom CNN: ~50–60% validation accuracy
- MobileNetV2 Transfer Learning: Achieved **100% validation accuracy**

---

## 🧠 Lesson Learned

> Transfer learning drastically outperforms small custom CNNs on limited datasets — especially when using powerful pretrained architectures like MobileNetV2.

---

## 📂 File

- [`horse-human-classification-cnn-vs-mobilenetv2.ipynb`](./horse-human-classification-cnn-vs-mobilenetv2.ipynb)

---

## 📸 Preview

*(Optional: Add training graphs or model summaries as images here)*

---

## 🧑‍💻 Author

Made with ❤️ by Amin
