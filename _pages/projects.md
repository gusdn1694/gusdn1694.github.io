---
title: "Projects"
permalink: /projects/
layout: single
author_profile: true
---
## Human-Factor-Based Wildfire Risk Prediction Model
**Period:** Mar 2025 – Jun 2025  

### Overview
Based on the fact that 71% of wildfires in the past 10 years were caused by human factors, this project aims to predict high-risk areas by training a CNN on fused data from satellite imagery and local residential (house-location) information.

### Pipeline

<p>
  <img src="/images/4ch_image.png" alt="4-channel image" style="max-width: 360px; height: 240px; margin-right: 12px;">
</p>

1. Collect Sentinel-2 imagery for the target region.
2. Load and rasterize the residential (housing) shapefile
3. Stack the rasterized mask with the original imagery to form 4-channel images.
4. Generate sliding-window patches (64×64).
5. Split patches into positive/negative using historical wildfire coordinates.
6. Train the CNN on the labeled pathces and run inference to produce riks predictions.

### Inference

<p>
  <img src="/images/fire_heatmap.png" alt="Fire Heatmap" style="max-width: 360px; height: 240px; margin-right: 12px;">
</p>

- Generated a heatmap from the model’s predictions.

### Recall / Confusion matrix

<p>
  <img src="/images/confusion_matrix.png"
       alt="Confusion Matrix"
       style="max-width: 360px; height: 240px; border: 0; box-shadow: none;">
</p>

- Achieved a recall of **76.8%** at a decision threshold of **0.9**.

### Planning
- Integrate additional human factors with environmental variables for better feature sets.
- Apply **domain adaptation** techniques to mitigate positive bias caused by data scarcity.
