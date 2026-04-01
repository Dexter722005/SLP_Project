# Emotion And Sentiment Analysis Using Multimodal Cues
# 📌 Multimodal Sentiment and Emotion Analysis using MVSA Dataset

## 🧠 Project Overview

This project implements a **multimodal deep learning system** that performs:

* **Sentiment Classification** (Positive / Negative / Neutral)
* **Emotion Classification** (Happy, Sad, Angry, Fear, etc.)

using:

* 🖼️ Images
* 📝 Text Captions

from the **MVSA-Single** and **MVSA-Multiple** datasets.

---

## 🚀 Key Features

* Multimodal learning (Image + Text)
* Pretrained models:

  * BERT (text feature extraction)
  * ResNet50 (image feature extraction)
* Emotion label generation using pretrained NLP model
* Feature fusion (concatenation of embeddings)
* Multi-task learning (sentiment + emotion)
* Full evaluation metrics:

  * Accuracy
  * Precision
  * Recall
  * F1-score
  * Confusion Matrix

---

## 📂 Dataset Description

The MVSA dataset contains:

```
MVSA/
 ├── data/
 │    ├── 0001.jpg
 │    ├── 0001.txt
 │    ├── 0002.jpg
 │    ├── 0002.txt
 │    └── ...
 ├── labelResultAll.txt
```

### Components:

* `.jpg` → Image
* `.txt` → Caption (text)
* `labelResultAll.txt` → Sentiment labels

### Sentiment Labels:

* Positive
* Negative
* Neutral

⚠️ Emotion labels are **not provided**, so they are generated using a pretrained model.

---

## 🧪 Methodology

### 1. Data Loading

* Extract image paths, captions, and sentiment labels
* Merge MVSA-Single and MVSA-Multiple

### 2. Data Preprocessing

* Remove missing images
* Remove empty captions
* Clean labels

### 3. Emotion Label Generation

* Use pretrained transformer model:

  * `distilbert-base-uncased-emotion`
* Apply confidence thresholding

---

## 🧠 Model Architecture

### 🔤 Text Processing

* Model: **BERT**
* Output: 768-dimension embedding

### 🖼️ Image Processing

* Model: **ResNet50**
* Output: 2048-dimension embedding

### 🔗 Feature Fusion

* Concatenate text + image features

### 🤖 Multi-Task Model

```
Input → Shared Layers → 
          ├── Sentiment Head (3 classes)
          └── Emotion Head (N classes)
```

---

## ⚙️ Training Details

* Loss Function: CrossEntropyLoss
* Optimizer: Adam
* Epochs: 10
* Feature Normalization: StandardScaler
* Dropout + BatchNorm for regularization

---

## 📊 Evaluation Metrics

### Sentiment & Emotion Evaluation:

* Accuracy
* Precision (Weighted)
* Recall (Weighted)
* F1 Score (Weighted)
* Classification Report
* Confusion Matrix

---

## 📈 Results

The model successfully:

* Learns multimodal features
* Predicts sentiment from dataset labels
* Generates and predicts emotion labels

Performance improves after:

* Feature normalization
* Better model architecture
* Confidence-based emotion labeling

---

## 📄 Output

Final predictions are saved as:

```
final_output.csv
```

### Format:

| image | text | predicted_sentiment | predicted_emotion |
| ----- | ---- | ------------------- | ----------------- |

---

## 🛠️ Technologies Used

* Python
* PyTorch
* Transformers (HuggingFace)
* Torchvision
* Scikit-learn
* Pandas
* Matplotlib

---

## ⚠️ Challenges Faced

* Missing emotion labels → solved via pretrained model
* Noisy captions → handled with cleaning
* Class imbalance → mitigated via filtering and thresholds
* High computation → solved using sampling

---

## 💡 Future Improvements

* Use attention-based fusion instead of concatenation
* Fine-tune BERT and ResNet
* Use larger dataset (full MVSA without sampling)
* Add real emotion datasets (e.g., GoEmotions)

---

## 🎯 Conclusion

This project demonstrates:

* Effective multimodal learning
* Integration of pretrained models
* Multi-task classification
* Real-world application of NLP + Computer Vision

---

## 🎤 Viva Explanation (Short)

> “We used MVSA dataset containing image-caption pairs for sentiment analysis. Since emotion labels were not available, we generated them using a pretrained transformer model. Then we extracted features using BERT and ResNet, fused them, and trained a multi-task neural network to predict both sentiment and emotion.”

---

## 👨‍💻 Author

* Name:
* Shreshth Panda 23BAI1155
* <br>Akshat Jain 23BAI1205<br>Adibhatla Sai Prashanth 23BAI1250
* Course: Speech and Language Processing (SLP)
* Project Type: Multimodal AI

---

