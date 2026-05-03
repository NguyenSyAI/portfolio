
---
layout: default
title: Vision–IMU Terrain Recognition
---

<h1 style="text-align:center; margin-top:20px;">
  <a href="YOUR_PDF_LINK_HERE"
     target="_blank"
     style="text-decoration:none; color:inherit;">
    Vision–IMU Fusion for Real‑Time Terrain Recognition in Assistive and Prosthetic Locomotion
  </a>
</h1>

## Role
Lead researcher — responsible for multimodal dataset collection (camera + IMU), terrain annotation, deep learning model development, fusion architecture design, and experimental validation across diverse indoor and outdoor terrains.

---

## Overview
This project introduces a **real‑time terrain recognition framework** that fuses **vision** and **IMU** data to classify walking environments for lower‑limb assistive devices such as prostheses, exoskeletons, and AFOs. The system is designed to support **adaptive control**, enabling devices to adjust stiffness, push‑off power, or gait mode based on upcoming terrain.

The dataset includes **multiple real‑world terrains**:

- Stairs (up/down)  
- Slopes (incline/decline)  
- Grass  
- Concrete  
- Gravel  
- Indoor flooring  

The fusion model integrates **CNN‑based visual features** with **IMU kinematic signals**, enabling robust classification even under motion blur, lighting changes, or sensor noise.

---

## System Summary

### **Multimodal Sensing**
- **Camera:** RGB frames capturing terrain geometry  
- **IMU:** 3‑axis accelerometer + gyroscope  
- **Sampling:** synchronized camera–IMU timestamps  
- **Mounting:** foot‑level or shank‑level for prosthesis integration  

### **Terrain Classes**
- Level ground  
- Grass  
- Concrete  
- Stairs up  
- Stairs down  
- Ramp up  
- Ramp down  

### **Dataset Characteristics**
- Thousands of labeled frames across multiple subjects  
- Outdoor + indoor environments  
- Variable lighting, speed, and gait patterns  
- Frame‑level and sequence‑level labels  

---

## Proposed Model

The **Vision–IMU Fusion Network** consists of:

### **1. Vision Branch**
- CNN backbone (ResNet/MobileNet)  
- Extracts spatial features from terrain images  
- Robust to lighting and texture variations  

### **2. IMU Branch**
- 1D CNN or LSTM  
- Learns temporal gait signatures  
- Captures slope transitions, foot orientation, and vibration patterns  

### **3. Fusion Layer**
- Concatenation or attention‑based fusion  
- Learns cross‑modal relationships  
- Produces final terrain classification  

### **4. Real‑Time Output**
- < 10 ms inference on embedded hardware  
- Suitable for prosthesis control loops  

---

### Key Findings
- Fusion significantly improves accuracy over single‑sensor models  
- IMU helps when vision suffers from blur or low light  
- Vision helps when IMU signals are ambiguous (e.g., level vs. slight incline)  
- Real‑time performance suitable for prosthesis control  

---

## Visualizations
## Visualizations
<div style="text-align:center; margin: 25px 0;">
  <video style="width:100%; max-width:650px; border-radius:10px;" controls>
    <source src="assets/0310(2)mp4.mp4" type="video/mp4">
  </video>
  <div style="font-size:16px; font-weight:600; margin-top:10px; color:#444;">
    Your Caption Here
  </div>
</div>



## Impact
This work enables **adaptive terrain‑aware control** for:

- Active ankle‑foot prostheses  
- Semi‑active AFOs  
- Robotic exoskeletons  
- Smart mobility assistance systems  

By recognizing terrain in real time, assistive devices can adjust stiffness, damping, and push‑off power to improve **safety**, **stability**, and **energy efficiency** for users.

