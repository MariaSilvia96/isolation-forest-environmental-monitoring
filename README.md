# Isolation Forest for Environmental Monitoring: A Data-Driven Approach to Land Management

This repository contains the Python implementation of the anomaly detection methodology described in the article **"Isolation Forest for Environmental Monitoring: A Data-Driven Approach to Land Management"** (Binetti et al., 2025), published in *Environments* (MDPI).

## Overview
This script applies an unsupervised Machine Learning approach (Isolation Forest) to multispectral satellite imagery to detect environmental anomalies, such as burned areas or degraded land patches. By evaluating the differences in specific spectral indices (NDVI, NBR, NDMI) over a given timeframe, the algorithm computes continuous anomaly scores to identify statistically significant alterations in the landscape.

## Reference and Citation
If you use this code or methodology in your research, please cite the original article:

> Binetti, M.S.; Uricchio, V.F.; Massarelli, C. Isolation Forest for Environmental Monitoring: A Data-Driven Approach to Land Management. *Environments* **2025**, *12*, 116. [https://doi.org/10.3390/environments12040116](https://doi.org/10.3390/environments12040116)

## Prerequisites
To run this script, you need Python 3.8+ and the following libraries:
- `numpy`
- `rasterio`
- `scikit-learn`
- `matplotlib`

You can install the required dependencies via pip:
```bash
pip install -r requirements.txt
