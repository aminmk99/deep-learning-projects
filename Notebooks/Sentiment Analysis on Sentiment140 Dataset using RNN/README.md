# 🧠 Sentiment Analysis on Sentiment140 Dataset using RNN

This notebook walks through a complete sentiment analysis pipeline on the **Sentiment140 dataset**, containing 1.6 million labeled tweets. We use **Recurrent Neural Networks (RNN)** with **learned word embeddings** to classify tweet sentiment as either **positive** or **negative**.

---

## 📦 Dataset Overview

- **Source**: [Sentiment140 on Kaggle](https://www.kaggle.com/datasets/kazanova/sentiment140)
- **Size**: 1.6 million tweets
- **Labels**:  
  - `0` → Negative sentiment  
  - `4` → Positive sentiment (mapped to `1` during preprocessing)

---

## 🔄 Preprocessing Steps

1. **Download and unzip** the dataset
2. **Load** data using `pandas`
3. **Normalize labels** (`4` → `1`)
4. **Clean tweets**:
   - Lowercase
   - Remove URLs, mentions, hashtags, special characters
5. **Tokenize** text to convert words into integer IDs
6. **Pad** sequences to a uniform length (`max_length = 32`)

---

## 🧠 Model 1: RNN with Learned Embeddings

- **Embedding layer**: initialized randomly, learned during training
- **LSTM layer**: 64 units
- **Dense layers** for classification
- **Binary cross-entropy loss**, `adam` optimizer

### 📈 Result:
- Validation accuracy plateaued around **82.6%**

---

## 🚀 Model 2: Improved RNN (Bidirectional LSTM + Dropout)

- **Bidirectional LSTM** (128 units)
- **More Dropout** for regularization
- Higher capacity and context-awareness

### 📈 Result:
- Slight improvement in accuracy
- Better generalization, but performance still plateaued

---

## ✅ Key Learnings

- Tokenization and padding are essential before embedding
- Learned embeddings work well, but GloVe could offer small gains
- Validation accuracy ~83% is common due to noise in tweets
- Regularization and bidirectionality help but won’t solve data quality limits

---

## 🧰 Next Steps

- Try **pretrained GloVe embeddings**
- Experiment with **GRU**, `Conv1D`, or transformer-based models
- Visualize predictions and errors
- Create a Kaggle notebook and share your approach with the community!

