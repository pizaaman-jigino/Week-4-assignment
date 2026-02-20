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

<!-- CONTEXT -->
Context
One of the main aims of the Sentinel-3 mission is to measure the Earth’s surface using radar altimetry, with applications including sea surface height, sea state, and cryosphere monitoring (e.g., sea ice).
Altimetry satellites transmit radar pulses towards the Earth. The part of the returned signal received by the sensor is the echo waveform. The shape and strength of this waveform depend on surface properties such as roughness and dielectric behaviour.
Because sea ice and open water leads have different physical characteristics, their echo waveforms tend to differ in measurable ways. This allows us to use waveform-derived features and clustering methods to distinguish between sea ice and leads.
<!-- MODELS -->
Unsupervised Learning Method: Gaussian Mixture Model (GMM)
In this assignment I use a Gaussian Mixture Model (GMM) to cluster echo-derived features into two groups. A GMM is a probabilistic clustering model that represents the data as a mixture of Gaussian components, typically fitted using the Expectation–Maximisation (EM) algorithm.
Key ideas behind GMM in this workflow:
Two components are used to represent two dominant surface classes (sea ice vs lead)
Each data point is assigned to the most likely Gaussian component (cluster)
Because cluster IDs (0/1) are arbitrary, clusters are aligned to the ESA classes before evaluation
Other unsupervised methods exist (e.g., K-means, DBSCAN, hierarchical clustering), but GMM is used here following the course template.
For reference:
scikit-learn documentation: https://scikit-learn.org/stable/modules/generated/sklearn.mixture.GaussianMixture.html
<!-- FUNCTIONS / WORKFLOW -->
Workflow Summary (Notebook)
The notebook week4_assignment.ipynb follows these main steps:
Load Sentinel-3 altimetry data from NetCDF (inside the .SEN3 product structure)
Extract waveform and waveform-derived variables/features (following the course template)
Remove invalid values (e.g., NaNs) and select relevant ESA classes (sea ice & lead)
Fit a 2-component GMM and predict cluster labels
Compute and plot:
Mean echo shape for sea ice and lead
Standard deviation for sea ice and lead
Compare predicted labels to ESA official classification using:
Confusion matrix
(Optional but included) classification report
<!-- RESULTS -->
Results
Mean echo shape (Sea Ice vs Lead)
The mean waveform is calculated for each predicted class. Standard deviation is also calculated to show variability within each class.
Confusion Matrix (GMM vs ESA official classification)
The confusion matrix quantifies agreement between the GMM-based classification and the ESA official labels.


