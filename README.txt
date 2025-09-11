# Peatland Breathing: Murnauer Moos

This repository demonstrates how to monitor peatland dynamics ("breathing") using **satellite remote sensing (radar + optical)** and **climate data**. The workflow integrates **Sentinel-1 SAR**, **Sentinel-2 NDVI**, and **CHIRPS rainfall** via the **Google Earth Engine Python API**.

##  Objective
To analyze **seasonal peatland ecohydrological dynamics** in the **Murnauer Moos peatland (Germany)** by combining:
- **Radar (Sentinel-1 VH/VV ratio)** → surface wetness proxy  
- **Optical (Sentinel-2 NDVI)** → vegetation greenness and productivity  
- **Climate (CHIRPS rainfall)** → precipitation driver  

## Study Area
**Murnauer Moos**, Bavaria, Germany – one of Central Europe’s largest continuous peatlands.  It is an important carbon sink and a biodiversity hotspot, making it an deal case study for eco-hydrological monitoring.  

## Data Sources
- [Sentinel-1 SAR (C-band, IW mode)](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S1_GRD)  
- [Sentinel-2 Surface Reflectance](https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S2_SR)  
- [CHIRPS Daily Rainfall](https://developers.google.com/earth-engine/datasets/catalog/UCSB-CHG_CHIRPS_DAILY)  


## ⚙️ Workflow
1. **Access datasets** with the Google Earth Engine Python API.  
2. **Process data:**
   - Compute monthly **VH/VV ratio** (Sentinel-1).  
   - Compute monthly **NDVI** (Sentinel-2).  
   - Aggregate **monthly rainfall totals** (CHIRPS).  
3. **Extract time series** over the peatland.  
4. **Visualize results** in Python using `matplotlib`.  


## Results
The VH/VV ratio increases with higher rainfall, indicating enhanced peat surface wetness. Conversely, as vegetation greenness (NDVI) rises during summer, the ratio declines, suggesting canopy growth dampens the radar signal. This highlights the coupled influence of rainfall and vegetation on peatland “breathing” dynamics in Murnauer Moos. 


##  Tools & Libraries
- Python 3.x  
- [Earth Engine Python API](https://developers.google.com/earth-engine/python_install)  

- Pandas, Matplotlib, Jupyter Notebook  
##  Future Work
This mini-project demonstrates the potential of multi-sensor analysis, but several extensions could strengthen peatland monitoring:  

- **InSAR displacement monitoring**: Using Sentinel-1 interferometry (with tools like SNAP or MintPy) to measure peat surface elevation changes linked to water-table dynamics.  
- **Carbon flux proxies**: Linking radar/NDVI indicators with field CO₂/CH₄ flux data  to develop predictive relationships.  
- **Machine learning approaches**: Using ML/AI to integrate multi-sensor datasets for improved spatio-temporal predictions of peatland condition.  
