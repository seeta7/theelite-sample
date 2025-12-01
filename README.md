# Medical Image Segmentation using Fuzzy Logic-Based U-Net (FPUA)

**Author:** Raju Yadav  
**Student ID:** 00020692  
**Supervisor:** Ramesh Paudyal  
**Institution:** Nilai University, Malaysia  
**Project Type:** Final Year Project / Capstone  
**Year:** 2025

This repository contains the implementation of a **Fuzzy Pooling U-Net (FPUA)** model for medical image segmentation.  
The system integrates **fuzzy logic** into the pooling layer to preserve important spatial features that traditional pooling methods (Max/Average) often lose. The model is designed to handle uncertainty, noise, and ambiguity in MRI, CT, and lesion images.

The project also includes a **Streamlit web interface** for real-time medical image segmentation.

---

## 📌 Overview

Traditional pooling layers used in CNNs remove essential boundary information, which leads to poor segmentation results in medical imaging. This project solves that by introducing:

### **Fuzzy Logic-Based Pooling**
- Gaussian Membership Functions  
- Local standard deviation estimation  
- K-middle mean smoothing  
- Fuzzy threshold calculation  
- Weighted pooling  

These techniques ensure that the most significant features are preserved during downsampling while reducing the impact of noise.

---

## ✨ Features

- Fuzzy-based pooling layer integrated into U-Net  
- Improved edge preservation in medical images  
- High accuracy segmentation performance across datasets  
- Data augmentation pipeline: rotation, flipping, scaling, noise  
- Evaluated using Dice, IoU, Accuracy, Precision, Recall  
- Streamlit UI for uploading and segmenting images  
- Ability to compare Max Pooling vs Average Pooling vs Fuzzy Pooling  

---

## 🧠 Method Summary

### **1. Preprocessing**
- Image resizing  
- Normalization  
- Noise filtering  
- Data augmentation (rotation, flips, zoom, shift)

### **2. Fuzzy Cue Generation**
- Gaussian membership computation  
- K-middle mean filtering  
- Local variance estimation  

### **3. Fuzzy Pooling Operation**
- Compute fuzzy threshold  
- Select dominant features  
- Apply weighted pooling instead of max/avg  
- Preserve fine structures and tumor boundaries  

### **4. Integration with U-Net**
- Replace max pooling layers in U-Net encoder with fuzzy pooling  
- Keep decoder + skip connections intact  

### **5. Model Evaluation**
- Dice Coefficient  
- Intersection over Union (IoU)  
- Accuracy  
- Precision  
- Recall  

---

## 📊 Results Summary

Accuracy comparison from evaluation:

| Model / Method | Pooling Type | Accuracy |
|----------------|--------------|----------|
| CNN (Max Pooling) | Deterministic | 84.7% |
| CNN (Avg Pooling) | Deterministic | 85.3% |
| ML (GLCM + SVM) | Manual Features | 81.2% |
| Attention UNet | Attention + Max | 94.4% |
| **Fuzzy Pooling U-Net (Proposed)** | **Fuzzy Logic** | **95.9%** |

Fuzzy pooling delivered the highest accuracy and best segmentation clarity.

---


---

## ⚙️ Installation

### **1. Clone the repository**
```bash
git clone https://github.com/RajuYadav1337/capstone_project.git
cd capstone_project
1. Create virtual environment--->python -m venv venv
Windows-->venv\Scripts\activate
Linux/macOS-->source venv/bin/activate

3. Install Dependencies
pip install -r requirements.txt

```
## 📌 requirements.txt
```bash
streamlit
torch
torchvision
opencv-python
numpy
pillow
matplotlib
scikit-learn
```

##🚀 Run the Application
```bash
Run this command to launch the Streamlit app:

streamlit run Main.py
```

MIT License

Copyright (c) 2025 Raju Yadav

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
