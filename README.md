# RemoteCLIP Improvements - Group 1

This repository contains our experiments and improvements on the RemoteCLIP model using various datasets and approaches. Below is a breakdown of the contents of this repository and the purpose of each notebook/script.

---

## 📁 File Overview

### 1. **`RemoteCLIP_colab_demo.ipynb`**
- **Description**: Base implementation of RemoteCLIP using the RN-50 backbone.
- **Contents**: 
  - Model inference
  - Baseline accuracy analysis
  - Sample visualizations of predictions

---

### 2. **`RemoteCLIP_improvement1_group1.ipynb`**
- **Improvement Focus**: Enhanced dataset creation by cropping bounding boxes from the RSIVGD dataset.
- **Model**: RN-50
- **Goal**: Test if using object-focused crops improves classification accuracy.

---

### 3. **`RemoteCLIP_improvement1_group1_ViT_B_32.ipynb`**
- **Improvement Focus**: Same cropped bounding box approach as above.
- **Model**: ViT-B/32
- **Goal**: Compare ViT-based model performance to RN-50 using the same dataset.

---

### 4. **`RemoteCLIP_improvement2_group1.ipynb`**
- **Improvement Focus**: 
  - Removed bounding boxes smaller than 1% of the original image (to reduce noise).
  - Upscaled remaining crops using Real-ESRGAN.
- **Goal**: Evaluate impact of resolution enhancement and noise reduction on classification accuracy.

---

### 5. **`cropping dataset.ipynb`**
- **Utility Script**: 
  - Performs bounding box-based cropping of original images.
  - Filters out bounding boxes smaller than 1% of the image size.
- **Used By**: Both Improvement 1 and Improvement 2 notebooks.

---

### 6. **`upscaling.ipynb`** 
- **Function**: Contains Real-ESRGAN code for upscaling cropped images.
- **Used In**: RemoteCLIP_improvement2_group1.ipynb

- 
### 7. **`evaluation_metrics.ipynb`**
- **Objective**: Originally intended to compute Recall@1, Recall@5, and Recall@10 as evaluation metrics.
- **Issue**: Due to memory constraints and long processing time (12+ hours despite optimization), the computation could not be completed successfully.
- **Outcome**: As a result, we used **top-2 accuracy** as our primary evaluation metric across all experiments.

---

## 📌 Summary

This project investigates how preprocessing techniques (like object-focused cropping and upscaling) and different model architectures affect the zero-shot classification performance of RemoteCLIP on satellite imagery.

---

## 🧑‍💻 Contributors

Maham Waseem 
Muhammad Ahmad
