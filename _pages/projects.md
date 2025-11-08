---
title: "Projects"
permalink: /projects/
layout: single
author_profile: true
---
## Human-Factor-Based Wildfire Risk Prediction Model
**Period:** Mar 2025 – Present  
**Advisor:** [Prof. Shin-Hoo Kang](https://shinhookang.github.io/)  
**Affiliation:** Dept. of Computer Convergence Software, Korea University Sejong Campus

### Overview
This project aims to predict wildfire-prone areas in the Gangwon/Chuncheon region by combining Sentinel-2 satellite imagery with human-activity-related information (residential-area shapefiles). Unlike approaches that rely only on meteorological or topographical factors, this work focuses on incorporating **human factors** to better reflect real-world fire occurrences in populated areas.

### Objectives
- Build a **4-channel input dataset** by merging Sentinel-2 RGB (4-3-2) imagery with a residential-area mask.
- Automate **sliding-window patch generation and labeling** based on historical fire occurrence points.
- Train a CNN-based binary classifier to distinguish “high-risk” vs. “non-risk” patches.
- Reconstruct patch-level predictions into a **risk heatmap** for visualization on a map.

### Data Pipeline
1. Collect Sentinel-2 imagery for the target region.
2. Load and rasterize the residential (housing) shapefile.
3. Stack the rasterized mask with the original imagery to form 4-channel images.
4. Generate sliding-window patches (e.g., 64×64).
5. Split patches into positive/negative using historical wildfire coordinates.
6. Apply basic augmentations (rotation, flip) and split into train/val sets.

### Tech Stack
- **Python**, **TensorFlow/Keras** (or PyTorch)
- **geemap / Google Earth Engine** for remote-sensing data
- **NumPy, rasterio/GDAL** for image/mask processing
- Visualization with confusion matrix / PR curve

### Current Status
- 1st version of 4-channel dataset (Sentinel-2 + residential mask) generated
- Patch-generation and positive/negative separation scripts implemented
- Baseline CNN training in progress
- Investigating class imbalance and positive-bias from overlapping patches

### Next Steps
- Integrate human factors with environmental variables for better feature sets
- Explore **domain adaptation** to transfer models across regions
- Prepare a write-up/report for later publication

