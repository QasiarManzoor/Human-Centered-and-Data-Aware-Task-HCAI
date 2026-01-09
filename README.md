# Human-Centered and Data-Aware Multi-Task Learning for Brain Tumor Analysis

This repository implements a **human-centered and data-aware deep learning framework** for **simultaneous brain tumor classification and segmentation** using MRI images.  
The approach leverages **multi-task learning** to jointly optimize diagnostic accuracy (classification) and interpretability (segmentation), aligning with responsible and explainable AI principles in medical imaging.

---

## 🔍 Key Features

- **Multi-task Learning Architecture**
  - Joint **tumor classification** (4 classes)
  - Pixel-level **tumor segmentation**
- **Human-Centered Design**
  - Emphasis on interpretability via segmentation overlays and heatmaps
  - Supports explainability tools (SHAP, LIME)
- **Data-Aware Training**
  - Balanced alternating optimization between tasks
  - Task-specific loss functions and scheduling
- **Strong Baselines**
  - ResNet-based encoders
  - U-Net-style decoder for segmentation
- **Comprehensive Evaluation**
  - Accuracy, Dice, IoU
  - Confusion matrix, ROC curves
  - Visual qualitative analysis

---

## 🧠 Tasks Supported

### 1. Brain Tumor Classification
Predicts one of the following classes:
- `glioma`
- `meningioma`
- `pituitary`
- `no_tumor`

**Loss Function:** Cross-Entropy Loss  
**Metrics:** Accuracy, Precision, Recall, F1-Score, ROC-AUC

---

### 2. Brain Tumor Segmentation
Produces a **binary tumor mask** aligned with the input MRI.

**Loss Function:**  
Binary Cross-Entropy + Dice Loss

**Metrics:**  
Dice Score, Intersection-over-Union (IoU)

---

## 🏗 Model Architecture

- Shared **ResNet Encoder**
- Classification head with global average pooling
- U-Net–style decoder for segmentation

---

## 📁 Dataset Structure

```
brisc2025/
├── classification_task/
│   ├── train/
│   └── test/
└── segmentation_task/
    ├── train/
    │   ├── images/
    │   └── masks/
    └── test/
        ├── images/
        └── masks/
```

---

## ⚙️ Installation

```bash
pip install torch torchvision timm shap lime scikit-learn matplotlib opencv-python
```

---

## 🚀 Training

The training loop alternates between classification and segmentation to maintain task balance.

---

## 📊 Evaluation

- Classification report
- Confusion matrices
- ROC & PR curves
- Dice/IoU curves
- Visual overlays and heatmaps

---

## 🧩 Explainability (XAI)

- SHAP
- LIME
- Grad-CAM visualizations

---

## 📄 License

For research and academic use only.

---

## 👤 Author

**Qaisar Manzoor**  
