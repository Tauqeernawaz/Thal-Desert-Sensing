# Windbreaks Calculation using Climatic Erosivity, Surface Roughness, and Soil Erodibility

This repository contains a script for calculating **Windbreaks** using key environmental factors: **Climatic Erosivity Factor (Fq)**, **Surface Roughness (D)**, and **Soil Erodibility (K)**, derived from precipitation, DEM (Digital Elevation Model), and slope data. The calculations are based on environmental proxies that represent these factors, processed using **Google Earth Engine (GEE)**.

The **Windbreaks** calculation integrates these factors to model erosion and land degradation processes, which are important for environmental monitoring and land management.

## Datasets:
1. **Precipitation Data (IMERG)**:
   - **Source**: [NASA GPM IMERG](https://developers.google.com/earth-engine/datasets/catalog/NASA_GPM_L3_IMERG_V06)
   - The **precipitation data** for the year 2019 was used to estimate **Climatic Erosivity Factor (Fq)**.

2. **Digital Elevation Model (SRTM)**:
   - **Source**: [USGS SRTM DEM](https://developers.google.com/earth-engine/datasets/catalog/USGS_SRTMGL1_003)
   - The **SRTM DEM** was used to calculate **surface roughness (D)** and **slope** (used as a proxy for **soil erodibility (K)**).

## Methodology:
1. **Climatic Erosivity Factor (Fq)**: 
   - This factor uses **precipitation** as a proxy for climatic erosivity, which plays a key role in soil erosion caused by rainfall.

2. **Surface Roughness (D)**: 
   - This factor represents the roughness of the surface. It is calculated by taking the **absolute difference** between the **DEM** and a **smoothed version of the DEM** (using focal mean). 

3. **Soil Erodibility (K)**: 
   - This factor is represented by **slope** (calculated from **DEM**). Steeper slopes typically have higher soil erosion potential.

4. **Windbreaks Calculation**: 
   - The final **Windbreaks** factor is derived by multiplying **Fq (Climatic Erosivity Factor)**, **D (Surface Roughness)**, and **K (Soil Erodibility)** to estimate areas most susceptible to erosion and degradation.

## Data Processing in Google Earth Engine:
The following steps were executed in **Google Earth Engine** to process and analyze the data:
1. **Precipitation Data**: Downloaded and filtered precipitation data for the year 2019 from the **NASA IMERG dataset**.
2. **DEM Data**: Downloaded **SRTM DEM** data and used it to calculate surface roughness and slope.
3. **Fq, D, and K Calculation**: The **Climatic Erosivity Factor (Fq)** was derived from precipitation, **Surface Roughness (D)** from DEM difference, and **Soil Erodibility (K)** from slope.
4. **Windbreaks**: The product of the three factors (**Fq**, **D**, and **K**) was calculated to model **windbreaks**.

## Geographical Coverage:
- **Region of Interest (ROI)**: The data is clipped to a **Region of Interest (ROI)**, which can be defined as a specific geographical area for the study.
- **Latitude**: [Insert latitude range of ROI]
- **Longitude**: [Insert longitude range of ROI]

## Data Format:
- The output of the calculations for **Fq**, **D**, and **K** are provided in **GeoTIFF** format.
- The **Windbreaks** output is also provided in **GeoTIFF** format for further analysis in GIS software such as **QGIS** or **ArcGIS**.

## License:
The data and code in this repository are made available under the **CC BY 4.0** (Creative Commons Attribution 4.0 International License), allowing reuse with proper attribution. You are free to use, modify, and distribute the data, provided you credit the source.

Alternatively, you may choose **CC0** (Public Domain Dedication) to make the data freely available for reuse without any restrictions.

## How to Use:
1. **Download the Data**: The **GeoTIFF** files for **Fq**, **D**, **K**, and **Windbreaks** are available for download.
2. **Run Scripts**: The provided **Google Earth Engine (GEE) scripts** process the data to calculate **Windbreaks**. 
   - Open **Google Earth Engine** and run the script to generate the datasets for your region of interest.
3. **Analysis and Visualization**: After downloading the **GeoTIFF** files, you can use **ArcGIS**, **QGIS**, or any other GIS software to analyze and visualize the data.

## Citation:
If you use this data in your research or publications, please cite the following:

## References:
- **Precipitation Data (IMERG)**: [NASA GPM IMERG Dataset](https://developers.google.com/earth-engine/datasets/catalog/NASA_GPM_L3_IMERG_V06)
- **Digital Elevation Model (SRTM)**: [USGS SRTM DEM](https://developers.google.com/earth-engine/datasets/catalog/USGS_SRTMGL1_003)
- **Google Earth Engine**: [Google Earth Engine Documentation](https://developers.google.com/earth-engine)
