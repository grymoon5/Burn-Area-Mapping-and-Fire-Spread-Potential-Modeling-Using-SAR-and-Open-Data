# SAR-Based Wildfire Burn Mapping and Spread Potential
1. 📍 Introduction

  This project is a lightweight prototype to create SAR-based wildfire monitoring products. It demonstrates how Sentinel-1 data can be used to map burned areas and generate    an initial fire spread potential model using open environmental data.

2. 🎯 Objective
- Detect burned areas using Sentinel-1 SAR imagery.
- Integrate terrain slope, wind direction, and vegetation to model fire spread potential.
- Visualize results through geospatial heatmaps and masks.
- Align with real-world use cases like ICEYE’s wildfire monitoring and disaster response efforts.

3. 🛠️ Tools & Data Used

| Component         | Tool                             | Source                      |
| ----------------- | -------------------------------- | --------------------------- |
| SAR Preprocessing | SNAP                             | Sentinel-1 GRD (Copernicus) |
| Burn Detection    | Python (`rasterio`, `numpy`)     | Exported GeoTIFF            |
| Slope             | SRTM DEM                         | NASA EarthData              |
| Wind              | Sample u/v wind data             | NOAA/ERA5                   |
| Vegetation        | ESA WorldCover or MODIS NDVI     | ESA/Copernicus              |
| Visualization     | Python (`matplotlib`, `seaborn`) | Google Colab                |

4. 🔍 Methodology
Part 1: Burn Area Detection
- Preprocessed Sentinel-1 data (apply orbit file, calibration, speckle filtering, terrain correction) using SNAP.
- Use pre- and post-event SAR images to detect intensity drops using log-ratio or dB difference.
- Applied threshold to isolate burn-affected areas.

Part 2: Spread Potential Modeling
- Derived slope from DEM data.
- Used wind direction (vector or raster) and vegetation cover as influencing layers.
- Created a weighted raster-based model combining slope, wind alignment, and vegetation as fuel load.
- Visualized potential spread areas using heatmaps and directional arrows.

Part 3: Visualisation
- Generate multi-band heatmaps for fire extent and spread.
- Export masks for GIS or remote sensing applications.

## 🔎 Sample Data

Mock raster datasets are included in the `data/` folder to test the workflow before applying real data.

5. 🗺️ Results

6. 📌 Key Takeaways
- Sentinel-1 SAR is effective for rapid burn mapping
- Fire spread modeling is feasible using open geodata and simple rules
- This prototype reflects early thinking around the kind of internal tools companies may be developing

7. ✨ Other areas to explore: 
- Refine burn detection with Otsu/adaptive thresholds
- Integrate real-time wind forecast data
- Use CNN or ML-based modeling for improved spread direction
- Adapt for EMEA wildfire-prone regions (Spain, France, Italy, Greece, Portugal, and Turkey)

8. 📬 Contact / Share
If you'd like to discuss the project, you can reach me at eaishwarya273@gmail.com or message me here on LinkedIn. Thanks for taking the time!

