## 🚀 Comparing Download Tools: `wget` vs `axel` vs `aria2c`

When downloading large files in a notebook or from the command line, choosing the right tool can save time and bandwidth. Here's how the three commonly used tools compare:

| Feature              | `wget`                     | `axel`                     | `aria2c`                               |
|----------------------|----------------------------|----------------------------|----------------------------------------|
| 🧠 Type              | General-purpose downloader | Download accelerator       | Advanced download utility              |
| ⚙️ Threads           | ❌ Single-threaded only     | ✅ Multi-threaded           | ✅ Multi-threaded                       |
| 📦 Protocols         | HTTP, HTTPS, FTP           | HTTP, HTTPS, FTP           | HTTP, HTTPS, FTP, BitTorrent, Metalink |
| 🔄 Resume support    | ✅ Yes                      | ✅ Yes                      | ✅ Yes                                  |
| 🔁 Recursive support | ✅ Yes (e.g., websites)     | ❌ No                       | ❌ No                                   |
| 📈 Speed             | Medium                     | Fast (parallel segments)   | Fast (highly configurable)             |
| 💻 Pre-installed?    | ✅ Often pre-installed      | ❌ Needs install            | ❌ Needs install                        |
| 🔧 Use case          | Reliable, simple downloads | Fast downloads (big files) | High-performance, flexible downloads   |

### 📝 Summary:

- **`wget`** is perfect for general use, automation scripts, or simple file downloads.
- **`axel`** is great when you want speed for large files and don’t need extra features.
- **`aria2c`** is the most powerful, especially when downloading multiple files or using advanced protocols.

---

<br>

## 📦 GloVe Embedding Files Explained

After unzipping `glove.6B.zip`, you’ll find the following files:
1. glove.6B.50d.txt
2. glove.6B.100d.txt
3. glove.6B.200d.txt
4. glove.6B.300d.txt

<br>
Each of these files contains **pretrained word embeddings** for 400,000 unique words, trained on a 6-billion-token corpus (Wikipedia + Gigaword 5). The only difference between them is the **embedding dimensionality**:

| File Name           | Embedding Dimension | File Size | Notes                                     |
|---------------------|---------------------|-----------|-------------------------------------------|
| `glove.6B.50d.txt`  | 50                  | ~171 MB   | Small, fast, less expressive              |
| `glove.6B.100d.txt` | 100                 | ~347 MB   | Balanced choice                           |
| `glove.6B.200d.txt` | 200                 | ~693 MB   | More expressive, moderate size            |
| `glove.6B.300d.txt` | 300                 | ~1 GB     | Most expressive, largest memory footprint |

---

### 🧠 What’s inside each file?

Each line represents a word and its vector, like this:
king 0.50421 0.22959 -0.10351 ... (n values)
- The first element is the **word** (e.g., `king`)
- The remaining elements are the **vector components** (float numbers)

---
### ✅ Which one should I use?

- **50d**: Good for quick tests or small models
- **100d / 200d**: Balanced performance and quality
- **300d**: Best semantic richness, but uses more memory

Choose based on the complexity of your task and available resources.

---

<br>

## 🧠 Word Analogy Task with Two Distance Metrics

In this exercise, we aim to solve a **word analogy** task using pretrained GloVe word embeddings. The task is to find a fourth word based on a relationship between three given words.

---

### 📜 Task Description

We are given three words:

- `word1`
- `word2`
- `word3`

The goal is to find a fourth word (`word4`) such that the relationship between `word3` and `word4` is similar to the relationship between `word1` and `word2`.

**Example:**

- word1 = Iran
- word2 = Tehran
- word3 = Germany
- Expected word4 = Berlin

<br>
We can represent this analogy in vector space as:

vector(word2) - vector(word1) + vector(word3) ≈ vector(word4)

---

### 🧮 Approach

We will implement this task using **two different distance/similarity metrics**:

#### 1. **Cosine Similarity**:
- Measures the **angle** between two vectors.
- Focuses on the **direction** (semantic meaning), regardless of vector length.
- **Commonly used** in NLP tasks because embeddings often vary in magnitude.

#### 2. **Euclidean Distance**:
- Measures the **straight-line (L2) distance** between vectors.
- Sensitive to **vector magnitude**, which can be misleading in high-dimensional spaces like word embeddings.

---

### 📊 Why Compare Both?

By implementing both approaches, we can observe:

- How each metric affects the **output word**.
- Whether both return the **same answer**, and if not, which one feels more accurate.
- That **cosine similarity typically performs better** for word embeddings, because:
  - It's **scale-invariant**
  - It better captures **semantic similarity**
  - It's the **standard** in most NLP tasks involving embedding comparisons

---

### ✅ Next Steps

We will:
1. Define a function that takes 3 words and an embedding dictionary.
2. Compute the target vector: `vec2 - vec1 + vec3`
3. Search for the most similar word using:
   - Cosine similarity
   - Euclidean distance
4. Compare and analyze the results
