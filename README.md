# 🌸 Flower Classification – Deep Learning (CNN) vs Classical ML (HOG + Boosting)

This project explores **two approaches** for classifying flower images into **5 categories**:

1. **Deep Learning (CNN with TensorFlow/Keras)** – learns features directly from raw pixel data.  
2. **Classical Machine Learning (HOG + Boosting Classifiers)** – uses handcrafted **Histogram of Oriented Gradients (HOG)** features with **CatBoost, LightGBM, and XGBoost**.

The comparison highlights the strengths of deep learning over traditional ML in image classification tasks.

---

## 📂 Dataset
- Source: Custom flower dataset ([Google Drive, ~145 MB](https://drive.google.com/file/d/1nzf5b_NNJlnInkueIWCOG7PWFv-Zk2Wk/view?usp=drive_link)).  
- Classes:
  - 🌺 Astilbe  
  - 🌻 Sunflower  
  - 🌼 Dandelion  
  - 🌸 Magnolia  
  - 🌹 Rose  

**Dataset Split:**
- 70% Training  
- 20% Validation  
- 10% Testing  


---

## 🏗️ Approach 1 – Convolutional Neural Network (CNN)

### 🔹 Model Architecture
- Conv2D → MaxPooling → Dropout  
- Conv2D → MaxPooling → Dropout  
- Flatten → Dense(256) → Dropout  
- Dense(5, softmax)

### 🔹 Training Details
- **Image Size:** 256 × 256 × 3  
- **Optimizer:** Adam  
- **Loss Function:** Sparse Categorical Crossentropy  
- **Batch Size:** 32  
- **Epochs:** 50  
- **Data Augmentation:** Random flip, rotation, zoom, contrast  

### 🔹 Results
- ✅ Training Accuracy: ~97%  
- ✅ Validation Accuracy: ~92–93%  
- ✅ **Test Accuracy: 90.25%**  

---

## 🏗️ Approach 2 – Classical ML (HOG + Boosting)

### 🔹 Feature Extraction
- Used **HOG (Histogram of Oriented Gradients)** to extract shape & edge features.  
- Each image → ~34,596 HOG features.  
- Features normalized using `MinMaxScaler`.  

### 🔹 Models Trained
- **CatBoostClassifier**  
- **LightGBMClassifier**  
- **XGBoostClassifier**

### 🔹 Results
| Model                | Accuracy | Precision | Recall | F1   | Balanced Acc. |
|-----------------------|----------|-----------|--------|------|---------------|
| **CNN (TensorFlow)** | **90.25%** | 0.91      | 0.90   | 0.90 | 0.89          |
| CatBoost             | 68.3%    | 0.69      | 0.68   | 0.68 | 0.65          |
| LightGBM             | 65.4%    | 0.67      | 0.65   | 0.65 | 0.61          |
| XGBoost              | 64.2%    | 0.65      | 0.64   | 0.63 | 0.60          |

✅ CNN significantly outperforms boosting classifiers.  
⚡ CatBoost was the best among classical ML models.

---

## 📈 Visualizations
- Training vs Validation Accuracy curves (CNN).  
- Confusion Matrices for CNN, CatBoost, LightGBM, and XGBoost.  
- Bar chart comparison of Accuracy, Precision, Recall, and F1 scores.  

---

## 🚀 How to Run

### 1️⃣ Clone the repository
```bash
git clone https://github.com/your-username/flower-classification.git
cd flower-classification
