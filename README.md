# Week-4-assignment
sea-ice and lead unsupervised learning
# GEOL0069 Week 4 — Unsupervised Altimetry Echo Classification (Sea Ice vs Lead)

This repository contains my Week 4 assignment for **GEOL0069: Artificial Intelligence for Earth Observation**.

## Task
Using **unsupervised learning**, classify Sentinel-3 altimetry echoes into **sea ice** and **leads**, then:
1. Compute the **average echo shape** and **standard deviation** for both classes.
2. Compare my classification against the **ESA official classification** using a **confusion matrix**.

This work builds on the provided notebook: *Chapter1_Unsupervised_Learning_Methods_Michel.ipynb*.

## Method (brief)
- Data: Sentinel-3 altimetry (NetCDF) waveforms and ESA surface-type flags.
- Features: waveform-derived metrics (e.g., backscatter / peakiness / SSD) following the course template.
- Model: **Gaussian Mixture Model (GMM)** with 2 components.
- Evaluation: labels aligned to ESA classes (sea ice / lead), then confusion matrix + classification report.

## Files
- `week4_assignment.ipynb` — main notebook (run this to reproduce results)
- `mean_echo.png` — mean echo shapes (sea ice vs lead)
- `conf_mat.png` — confusion matrix (GMM vs ESA)

## Results
**Mean echo shapes (Sea ice vs Lead)**  
![Mean echo](mean_echo.png)

**Confusion matrix (GMM vs ESA)**  
![Confusion matrix](conf_mat.png)

## How to run
### Option A: Google Colab (recommended)
1. Open `week4_assignment.ipynb` in Colab.
2. Mount Google Drive (if required by your data path).
3. Run all cells.

### Option B: Local
Install dependencies (typical):
- `numpy`, `matplotlib`, `scikit-learn`, `netCDF4`

Then run the notebook:
- Open `week4_assignment.ipynb` and run all cells.

## Notes
- Large raw data files are not uploaded to GitHub. Update the data path in the notebook to match your local/Drive setup.
