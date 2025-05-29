# 🛍️ Shoplifting Detection using Deep Learning

This project implements a deep learning-based video classification system to detect shoplifting activities in surveillance footage. The final model was deployed via a Django web application, offering real-time classification to assist retail store security.

---

## 📂 Dataset Description

The dataset contains videos categorized into:

* **Shoplifters:** 324 videos
* **Non-Shoplifters:** 531 videos

Each video represents a scenario inside a retail store, with varying movements and camera angles.

---

## 🛠️ Data Preprocessing

The preprocessing involved:

1. **Frame Extraction**:

   * 20 frames were extracted per video using OpenCV.
   * All frames were resized to 64×64 pixels.
   * Frames were normalized and compiled into sequences for model input.

2. **Dataset Splitting**:

   * The dataset was randomly split into:

     * **Training set:** 70%
     * **Validation set:** 15%
     * **Test set:** 15%

---

## 🧠 Model Architecture and Training

The model is a **ConvLSTM** based architecture designed for spatiotemporal video data:

* **Layers Used**:

  * `ConvLSTM2D` for capturing temporal and spatial features.
  * `MaxPooling3D`, `Dropout`, and `BatchNormalization` for regularization.
  * `Flatten` and `Dense` layers for final classification.

* **Training Details**:

  * **Loss Function**: Binary Crossentropy
  * **Optimizer**: Adam
  * **Metrics Tracked**: Accuracy, Precision, Recall
  * **Callbacks**: EarlyStopping, ReduceLROnPlateau, and ModelCheckpoint

---

## 📈 Results

* **Validation Accuracy:** 100%
* **Validation Precision & Recall:** High performance across all metrics
* **Test Set Accuracy:** Achieved **100% accuracy** on 129 test videos, indicating excellent generalization.

---

## 🚀 Model Deployment

The trained model was integrated into a Django-based web application:

* **Functionality**: Real-time classification of uploaded surveillance videos.
* **Use Case**: Designed for retail store security.
* **Performance**: Achieved **100% accuracy** on real-world test cases within the app.

