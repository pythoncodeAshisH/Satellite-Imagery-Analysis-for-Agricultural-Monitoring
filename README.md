# Satellite Imagery Analysis for Agricultural Monitoring

Objective: Develop a Python-based tool to analyze time-series satellite imagery for monitoring the health and progress of individual agricultural fields.


## Getting Started
This guide outlines the use of Python frameworks for analyzing Sentinel-2 data for agricultural purposes.

### Prerequisites
- Python 3.x
- Required Libraries: 
  - sentinelsat
  - rasterio
  - gdal
  - s2cloudless
  - earthengine-api
  - pandas
  - numpy
  - scikit-learn
  - tensorflow
  - matplotlib
  - reportlab
  - geemap (optional)

### Installation
For installation on Google Colab, use the following command for each package:
\```python
!pip install {package_name}
\```

### Earth Engine Authentication
Authenticate your Google Earth Engine account before running the scripts. Register here: [Google Earth Engine Registration](https://code.earthengine.google.com/register)
Additionally, create an account for Sentinel-2 data access: [Copernicus Open Access Hub Registration](https://browser.dataspace.copernicus.eu/)

## Task

### Data Retrieval
Scripts are available for downloading satellite images for a specific region and time period, including cloud cover filtering.
1) Python script to download Sentinel datasets. Fill in your username, password, start/end dates, and cloud cover percentage.
2) For manual download due to timeouts, visit [Copernicus Open Access Hub](https://browser.dataspace.copernicus.eu/).
3) Use Google Earth Engine (GEE) maps within Colab for location and Area of Interest (AOI) selection.

### Pre-Processing
Includes atmospheric correction, geometric correction, and cloud masking.
1) Sentinelsat Framework:
   - Atmospheric Correction: Download Sen2Cor-02.10.01 from [Sen2Cor Download](https://step.esa.int/main/snap-supported-plugins/sen2cor/sen2cor-v2-10/). Use CMD CLI for execution.
   - Geometric Correction: Process files like 'T43QEB_20240101T052221_B02_10m.jp2', saving output as .tif in Colab.
   - Cloud Masking: Install 'rasterio' and 's2cloudless', input file is 'GeometricCorrection.tif', output includes cloud mask and masked images.

2) Google Earth Engine (GEE):
   - Atmospheric and Geometric Correction: GEE automatically performs these tasks.
   - Cloud Masking: Select the 'QA60' file in GEE.

### Vegetation Index Calculation
Scripts calculate NDVI and EVI for the downloaded images, analyzing their variation over time.
- Sentinelsat Framework
- Google Earth Engine (GEE)

### Data Visualization
Scripts for visualizing the time-series analysis of vegetation indices through graphs and maps.
- Sentinelsat Framework
- Google Earth Engine (GEE)

### Prediction Model
Includes a Deep Learning-based LSTM model to predict future trends. Train the model for 100 epochs.

### Report Generation
Utilize the 'reportlab' package for automated summary report generation, including key statistics and visualizations.

## Running the Scripts
To run scripts in Colab, click on 'Runtime' in the main menu and select 'Run all'. Ensure all scripts and dependencies are properly configured.
"""
