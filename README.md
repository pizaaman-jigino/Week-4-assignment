# Week-4-assignment
sea-ice and lead unsupervised learning
# GEOL0069 Week 4 — Unsupervised Altimetry Echo Classification

## Getting Started
This repository contains my Week 4 assignment for **GEOL0069: Artificial Intelligence for Earth Observation (AI4EO)**.  
The aim is to use **unsupervised learning** to classify Sentinel-3 altimetry echoes into **sea ice** and **leads**, then compare the result against the **ESA official surface-type classification**.

This work is based on and extends the provided course notebook:  
*Chapter1_Unsupervised_Learning_Methods_Michel.ipynb*.

### Prerequisites
This project is intended to run in **Google Colab** (recommended) or locally.

- Core Python packages:
  - `numpy`, `matplotlib`, `scikit-learn`, `netCDF4`

If running in Colab, you may need (depending on your notebook):
```python
from google.colab import drive
drive.mount('/content/drive')
