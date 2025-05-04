
# 🌿 Plant Leaf Disease Classification using CNN and ResNet50V2

This project presents a deep learning-based image classification system for detecting and distinguishing between **Healthy**, **Early Blight**, and **Late Blight** leaf conditions. Two different models were trained and evaluated on the same dataset:

- A **custom CNN** built from scratch
- A **fine-tuned ResNet50V2** using transfer learning

Both models include a **data augmentation layer** to enhance model robustness.

---

## 📁 Dataset Structure

The dataset is organized into three standard splits:

```
PLD_3_Classes_256/
├── Training/
│   ├── Healthy/
│   ├── Early_Blight/
│   └── Late_Blight/
├── Validation/
│   ├── Healthy/
│   ├── Early_Blight/
│   └── Late_Blight/
└── Testing/
    ├── Healthy/
    ├── Early_Blight/
    └── Late_Blight/
```

Images are resized to 224x224 during preprocessing using `image_dataset_from_directory`.

---

## 🧠 Model Overview

This project compares two different model architectures for classifying plant leaf conditions. **Both models integrate a data augmentation layer** to improve generalization and reduce overfitting:

### 1. 🛠️ Custom CNN (Built from Scratch)
- Includes data augmentation (random flips, rotations, zooms)
- Lightweight convolutional layers with dropout and max-pooling
- Achieved **95.8% test accuracy**

### 2. 🔁 ResNet50V2 (Transfer Learning)
- Uses a pre-trained ResNet50V2 backbone (ImageNet)
- Data augmentation applied before feeding into the base model
- Fine-tuned by unfreezing the last few layers
- Achieved **93.3% test accuracy**

---

## 🚀 Pipeline Overview

### 1. 🧹 Data Loading & Preprocessing
- Images are batched and loaded using `image_dataset_from_directory`
- Resized to 224×224 and normalized
- **Data Augmentation** layer applied during training to:
  - Randomly flip (horizontal & vertical)
  - Apply slight rotations
  - Perform zoom transformations

### 2. 🧠 Model Training
- EarlyStopping monitors validation loss
- Separate training procedures for each model:
  - From-scratch CNN
  - Transfer learning with ResNet50V2

### 3. 📊 Evaluation
- Final models are evaluated using:
  - Classification Report (Precision, Recall, F1)
  - Normalized Confusion Matrix
  - Accuracy & Loss plots
  - Visualized predictions with correct/incorrect labels

---

## 📂 Repository Contents

| File | Description |
|------|-------------|
| `notebook.ipynb` | Full model pipeline |
| `README.md` | Project documentation |
| `PLD_3_Classes_256/` | Input dataset (user-provided, not included in repo) |

---

## ✅ Results Summary

| Model                  | Test Accuracy |
|------------------------|---------------|
| Custom CNN             | **95.8%**     |
| Fine-tuned ResNet50V2  | **93.3%**     |

---

## 👨‍💻 Author

**Ali Adel**
