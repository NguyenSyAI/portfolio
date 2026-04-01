---
layout: default
title: Home
---

# Sy Nguyen
PhD Researcher in Robotics & Biomechanics  

---

# 🚀 Projects

<style>
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

.card {
  position: relative;
  overflow: hidden;
  border-radius: 12px;
  cursor: pointer;
  text-decoration: none;
  color: black;
}

.card img {
  width: 100%;
  height: 220px;
  object-fit: cover;
  transition: transform 0.4s ease;
}

.card:hover img {
  transform: scale(1.08);
}

.overlay {
  position: absolute;
  bottom: 0;
  background: rgba(0,0,0,0.6);
  color: white;
  width: 100%;
  padding: 15px;
  transition: 0.3s;
}

.card:hover .overlay {
  background: rgba(0,0,0,0.85);
}

.title {
  font-size: 18px;
  font-weight: bold;
}

.desc {
  font-size: 13px;
}
</style>

<div class="grid">

<a href="project_gait.html" class="card">
  <img src="assets/img/imu_plot.png">
  <div class="overlay">
    <div class="title">Gait Event Detection</div>
    <div class="desc">IMU + Deep Learning</div>
  </div>
</a>

<a href="project_pushoff.html" class="card">
  <img src="assets/img/gait_example.gif">
  <div class="overlay">
    <div class="title">Push-Off Prediction</div>
    <div class="desc">Critical gait phase</div>
  </div>
</a>

<a href="project_experiment.html" class="card">
  <img src="assets/img/experiment.jpg">
  <div class="overlay">
    <div class="title">Experiment</div>
    <div class="desc">Human walking trials</div>
  </div>
</a>

<a href="project_model.html" class="card">
  <img src="assets/img/model_pipeline.png">
  <div class="overlay">
    <div class="title">Model</div>
    <div class="desc">CNN + LSTM</div>
  </div>
</a>

</div>

---

## 👋 About Me
I am a PhD researcher working on human gait analysis using wearable IMU sensors and deep learning.

My research focuses on detecting gait events and predicting push-off timing for assistive devices.

---

## 🔬 Research Focus
- IMU-based gait analysis  
- Deep learning  
- Assistive robotics  
