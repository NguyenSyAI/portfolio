---
layout: default
title: DeepCNN‑Swin Transformer Gait Event Detection
---

<h1 style="text-align:center; margin-top:20px;">
  <a href="YOUR_PDF_LINK_HERE"
     target="_blank"
     style="text-decoration:none; color:inherit;">
    DeepCNN‑Swin Transformer‑Based Gait Cycle Event Prediction for Adaptive Push‑Off Control
  </a>
</h1>

## Role
Lead researcher — responsible for dataset design, IMU instrumentation, gait event annotation, deep learning model development, Swin Transformer integration, experimental validation, and performance benchmarking across subjects and walking speeds.

---

## Overview
This project introduces a **DeepCNN‑Swin Transformer framework** for real‑time gait event detection using only **two IMUs** (shank + foot). Unlike conventional methods that detect only Heel Strike (HS), Foot Flat (FF), and Toe Off (TO), this work identifies **six gait events**, including two critical push‑off‑related events:

- Maximum Acceleration Down (MAD)  
- Maximum Acceleration Up (MAU)

These events provide **precise timing cues** for adaptive push‑off control in prostheses, AFOs, and powered ankle exoskeletons.

A treadmill dataset was collected from **10 participants** across **three walking speeds**, with each trial lasting 3 minutes. The proposed model achieved a **macro F1‑score of 0.951**, outperforming state‑of‑the‑art deep learning architectures.

---

## System Summary

### **Instrumentation**
- Six IMUs placed on both legs (only shank + foot used for this study)
- 3‑minute treadmill trials at slow, normal, and fast speeds
- Speed normalized using leg length (K = 0.27, 0.41, 0.55)

### **Gait Events Detected**
- Heel Strike (HS)  
- Maximum Acceleration Down (MAD)  
- Foot Flat (FF)  
- Heel Rise (HR)  
- Maximum Acceleration Up (MAU)  
- Toe Off (TO)  

### **Dataset Characteristics**
- 16 IMU features (acceleration, gyroscope, norms)
- Standardized inputs (mean = 0, std = 1)
- Class imbalance addressed via:
  - Gaussian noise augmentation  
  - Random scaling  
  - Thick labeling (±2 samples around each event)  
- Five‑fold cross‑validation across subjects

---

## Proposed Model
The **DeepCNN‑Swin Transformer** architecture integrates:

- **1D Convolutional Stem**  
  Extracts low‑level temporal features  
- **Residual CNN Blocks**  
  Captures fine‑grained gait transitions  
- **Patch Embedding Layer**  
  Converts signals into sequential tokens  
- **Swin Transformer Blocks**  
  Window‑based + shifted‑window self‑attention  
  → captures long‑range temporal dependencies  
- **Global Average Pooling + FC Layer**  
  Outputs 6‑class gait event predictions  

This hybrid design enables the model to learn both **local kinematic cues** and **global gait cycle structure**, essential for detecting push‑off‑related events.

---

## Experimental Results

### **Overall Performance (All Subjects)**

<table style="width:100%; text-align:center; border-collapse: collapse;">
  <tr style="background:#f2f2f2;">
    <th style="padding:8px; border:1px solid #ccc;">Model</th>
    <th style="padding:8px; border:1px solid #ccc;">Precision</th>
    <th style="padding:8px; border:1px solid #ccc;">Recall</th>
    <th style="padding:8px; border:1px solid #ccc;">F1</th>
  </tr>

  <tr><td>SVM</td><td>0.071</td><td>0.217</td><td>0.224</td></tr>
  <tr><td>KNN</td><td>0.790</td><td>0.801</td><td>0.795</td></tr>
  <tr><td>Decision Tree</td><td>0.847</td><td>0.853</td><td>0.849</td></tr>
  <tr><td>LDA</td><td>0.853</td><td>0.898</td><td>0.869</td></tr>
  <tr><td>MLP</td><td>0.938</td><td>0.946</td><td>0.942</td></tr>
  <tr><td>DNN</td><td>0.940</td><td>0.945</td><td>0.942</td></tr>
  <tr><td>LSTM‑DNN</td><td>0.936</td><td>0.928</td><td>0.930</td></tr>

  <tr style="font-weight:bold; background:#e8f5e9;">
    <td>Proposed DeepCNN‑Swin</td>
    <td>0.949</td>
    <td>0.954</td>
    <td>0.951</td>
  </tr>
</table>

### Key Findings
- **Highest macro F1‑score (0.951)** among all models  
- **Perfect accuracy** for HS and TO  
- **Strong MAU detection (0.97 accuracy)** → critical for push‑off timing  
- **Robust across slow, normal, and fast walking speeds**  
- **Swin Transformer improves long‑range temporal modeling**  

---

## Visualizations (Optional)
You can insert your learning curves, confusion matrix, or architecture figure here using:

```html
<img src="assets/YOUR_IMAGE.png" style="width:100%; border-radius:10px;">
