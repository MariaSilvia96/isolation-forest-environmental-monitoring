# Isolation Forest for Environmental Monitoring: A Data-Driven Approach to Land Management

This repository contains the Python implementations of the anomaly detection methodologies described in the article **"Isolation Forest for Environmental Monitoring: A Data-Driven Approach to Land Management"** (Binetti et al., 2025), published in *Environments* (MDPI).

## Overview
This project applies an unsupervised Machine Learning approach (Isolation Forest) to multispectral satellite imagery to detect environmental anomalies. The repository includes two distinct case studies addressed in the article:
1. **Burned Area Detection:** Evaluating differences in NDVI, NBR, and NDMI indices to identify areas affected by wildfires.
2. **Land Degradation and Quarry Expansion:** Evaluating spatiotemporal changes using NDVI, EVI, and SAVI indices to monitor long-term land-use alterations.

By computing continuous anomaly scores based on these spectral indices, the algorithm identifies statistically significant alterations in the landscape over a given timeframe.

## Reference and Citation
If you use this code or methodology in your research, please cite the original article:

> Binetti, M.S.; Uricchio, V.F.; Massarelli, C. Isolation Forest for Environmental Monitoring: A Data-Driven Approach to Land Management. *Environments* **2025**, *12*, 116. [https://doi.org/10.3390/environments12040116](https://doi.org/10.3390/environments12040116)

## Repository Structure
The analysis is divided into two separate Jupyter Notebooks:
* `burned_area_detection_spectralindex_Isolation_forest.ipynb`: Focuses on acute events (wildfires) using the NDVI, NBR, and NDMI triad.
* `anomaly_detection_spectralindex_Isolation_forest.ipynb`: Focuses on long-term land degradation (quarry expansion) using the NDVI, EVI, and SAVI triad.

## Prerequisites
To run these scripts, you need Python 3.8+ and the following libraries:
- `numpy`
- `rasterio`
- `scikit-learn`
- `matplotlib`

You can install the required dependencies via pip:
```bash
pip install -r requirements.txt

## Data Requirements
Due to storage limitations and standard version control practices, the original spatial `.tif` files are not included in this repository.

To reproduce the analyses, researchers must provide their own georeferenced raster files and place them in a local `data/` directory.

### Case Study 1: Burned Area Detection
1. **NDVI difference raster** (e.g., `NDVI_diff_august_may_2024.tif`)
2. **NBR difference raster** (e.g., `NBR_diff_august_may_2024.tif`)
3. **NDMI difference raster** (e.g., `NDMI_diff_august_may_2024.tif`)
4. **Ground truth binary raster** (optional, required only for ROC/AUC validation)

### Case Study 2: Quarry Expansion / Land Degradation
1. **NDVI temporal difference raster** (e.g., `NDVI_diff_2024_2017.tif`)
2. **EVI temporal difference raster** (e.g., `evi_difference.tif`)
3. **SAVI temporal difference raster** (e.g., `savi_difference_2024_2017.tif`)
4. **Ground truth binary raster** (optional, e.g., `raster_verità_a_terra_CAVA.tif`, required only for ROC/AUC validation)

*Methodological Note: The algorithm mathematically requires continuous float values for the spectral indices. The scripts automatically standardize the spatial profiles (resolution, CRS, bounding box) based on the first raster and apply a strict boolean mask to exclude `NoData` (NaN) pixels prior to the Machine Learning phase.*

## Usage Instructions
1. Clone this repository to your local machine.
2. Create a directory named `data/` in the root folder of the project.
3. Place your pre-processed `.tif` files inside the newly created `data/` folder.
4. Launch Jupyter Notebook or JupyterLab from your command line terminal.
5. Open the notebook corresponding to your analysis of interest and execute all cells sequentially.
