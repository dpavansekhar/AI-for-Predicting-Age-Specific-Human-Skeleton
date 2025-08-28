# 🦴 Bone Age Prediction with Deep Learning

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)
![Keras](https://img.shields.io/badge/Keras-Deep%20Learning-red.svg)
![Status](https://img.shields.io/badge/Project-Active-success.svg)

---

## 📖 Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Models Implemented](#models-implemented)
- [Grad-CAM Explainability](#grad-cam-explainability)
- [Results](#results)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Future Work](#future-work)
- [References](#references)

---

## 🔎 Overview
This repository focuses on **Bone Age Assessment** using advanced **Convolutional Neural Networks (CNNs)**.  
Bone age prediction is critical in diagnosing growth disorders in children. The project leverages multiple **state-of-the-art architectures** such as **EfficientNet**, **ResNet101**, and **Xception**, alongside **Grad-CAM visualizations** for explainability.  

The goal is to:
- Improve accuracy in age estimation from X-ray images.  
- Compare different architectures’ performance.  
- Provide interpretability via Grad-CAM heatmaps.  

---

## 📂 Dataset
We use the **RSNA Pediatric Bone Age dataset**, which contains **X-ray images of hands** annotated with bone ages.  

- Source: [RSNA Bone Age Challenge](https://www.kaggle.com/datasets/kmader/rsna-bone-age/)  
- Preprocessing steps:
  - Rescaling images to a fixed input size.  
  - Normalization for stable training.  
  - Augmentation (rotation, flipping, scaling) for robustness.  

---

## 🧠 Models Implemented

### ✅ EfficientNetB0
- Lightweight model, optimized for speed and accuracy.  
- Good for baseline comparisons.  

### ✅ EfficientNetB5
- Larger EfficientNet variant with more layers & parameters.  
- Higher accuracy at cost of computation.  

### ✅ ResNet101
- Deep residual network with skip connections.  
- Handles vanishing gradients effectively.  

### ✅ Xception
- Depthwise separable convolutions for efficiency.  
- Strong performance in image classification tasks.  

---

## 🎨 Grad-CAM Explainability
To ensure **trustworthy AI in healthcare**, we apply **Grad-CAM** to visualize which regions of X-rays influence predictions.  

Example visualization:  

![Grad-CAM Example](https://github.com/user-attachments/assets/bc9c20aa-9f4b-49b4-a68e-a4853f28b586)

---

## 📊 Results

| Model            | Classification Model |Regression Model | Notes |
|------------------|----------------------|-----------------|-------|
| EfficientNetB0   | 87.00%               | 8.13            | Baseline |
| EfficientNetB5   | 87.10%               | 8.37            | Best performing EfficientNet |
| ResNet101        | 86.95%               | 9.56            | Stable, deep model |
| Xception         | 86.58%               | 6.82            | Good trade-off between accuracy and efficiency |


---

## ⚙️ Installation

```bash
# Clone this repository
git clone https://github.com/dpavansekhar/AI-for-Predicting-Age-Specific-Human-Skeleton.git
cd AI-for-Predicting-Age-Specific-Human-Skeleton

# Create a virtual environment
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt 
```

---

## Project Structure

``` bash
📦 bone-age-prediction
 ┣ 📂 images
 | ┣ Thirteen-short-bones-in-the-hand-and-wrist-observed-in-the-scoring-system-based-on-the_W640.jpg
 ┣ 📂 notebooks
 ┃ ┣ EfficientNetB0.ipynb
 ┃ ┣ EfficientNetB5, ResNet101 & Xception.ipynb
 ┃ ┣ GradCAM.ipynb
 ┃ ┣ RSNA Bone Age Model Testing.ipynb
 ┣ 📂 outputs
 ┃ ┣ 📂 EfficientNetB0
 ┃ ┃ ┣ EffecientnetB0_Reg.keras
 ┃ ┃ ┣ EffecientnetB0.keras
 ┃ ┣ 📂 EfficientNetB5
 ┃ ┃ ┣ EfficientnetB5_reg.keras
 ┃ ┃ ┣ EfficientnetB5.keras
 ┃ ┃ ┣ history_eff_reg.pkl
 ┃ ┃ ┣ history_eff.pkl
 ┃ ┣ 📂 ResNet101
 ┃ ┃ ┣ history_res_reg.pkl
 ┃ ┃ ┣ history_resnet.pkl
 ┃ ┃ ┣ Resnet101_reg.keras
 ┃ ┃ ┣ Resnet101.keras
 ┃ ┣ 📂 Xception
 ┃ ┃ ┣ history_xcp_reg.pkl
 ┃ ┃ ┣ history_xcp.pkl
 ┃ ┃ ┣ Xception_reg.keras
 ┃ ┃ ┣ Xception.keras
 ┣ 📂 research papers
 ┃ ┣ 📚 1.pdf
 ┃ ┣ 📚 2.pdf
 ┃ ┣ 📚 3.pdf
 ┃ ┣ 📚 4.pdf
 ┃ ┣ 📚 5.pdf
 ┃ ┣ 📚 6.pdf
 ┣ 📜 requirements.txt
 ┣ 📜 README.md
 ┗ 🔧 .gitattributes 
```

---

## 🔮 Future Work

1. Incorporate Vision Transformers (ViT).
2. Deploy as a Flask/Django Web App for doctors.
3. Explore multi-task learning (gender + bone age).

---

## 📚 References

1. RSNA Pediatric Bone Age Dataset - Kaggle
2. EfficientNet Paper: Tan & Le, 2019
3. ResNet Paper: He et al., 2016
4. Xception Paper: Chollet, 2017
5. Grad-CAM Paper: Selvaraju et al., 2017
