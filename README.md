# 🌸 Flower Classification using CNN

This project implements a **Convolutional Neural Network (CNN)** to classify flower images into **5 categories**.  
The model was trained on the **Kaggle Flower Dataset**, achieving over **90% test accuracy**.

---

## 📂 Dataset
- Dataset: [Kaggle Flowers Recognition](https://www.kaggle.com/alxmamaev/flowers-recognition)  
- Classes:  
  - 🌹 Rose  
  - 🌻 Sunflower  
  - 🌼 Daisy  
  - 🌸 Dandelion  
  - 🌷 Tulip  

The dataset was split into:
- **70% Training**
- **20% Validation**
- **10% Testing**

---

## 🏗️ Model Architecture
The CNN was built using **TensorFlow/Keras** with the following structure:

- `Conv2D` + `MaxPooling` layers (feature extraction)  
- `Dropout` (to reduce overfitting)  
- `GlobalAveragePooling2D` (dimensionality reduction)  
- Fully Connected Dense layers (classification)  
- Final `Softmax` layer for 5-class output  

---

## ⚙️ Training Details
- **Image size:** 224 × 224 × 3  
- **Optimizer:** Adam (`lr = 0.001`)  
- **Loss function:** Categorical Crossentropy  
- **Batch size:** 32  
- **Epochs:** 50  
- **Callbacks:**
  - `ModelCheckpoint` (save best model)
  - `EarlyStopping` (prevent overfitting)
  - `ReduceLROnPlateau` (learning rate scheduler)

---

## 📊 Results
- ✅ **Training Accuracy:** ~97%  
- ✅ **Validation Accuracy:** ~92–93%  
- ✅ **Test Accuracy:** **90.25%**  

Training vs Validation Accuracy Plot:  
*(Add your matplotlib plot here)*

Confusion Matrix:  
*(Optional: insert confusion matrix visualization here)*

---

## 🚀 How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/flower-classification-cnn.git
   cd flower-classification-cnn
