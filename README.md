# Peatland Breathing: Murnauer Moos

This repository demonstrates how to monitor peatland dynamics ("breathing") using multi-source satellite remote sensing (radar + optical) and climate data. The workflow integrates Sentinel-1 SAR, Sentinel-2 NDVI, CHIRPS rainfall datasets via the Google Earth Engine Python API, and **InSAR displacement**.

## Objective

Analyze seasonal peatland ecohydrological dynamics in the Murnauer Moos peatland (Germany) by combining:

- **Radar (Sentinel-1 VH/VV ratio):** Proxy for surface wetness
- **Optical (Sentinel-2 NDVI):** Vegetation greenness and productivity
- **Climate (CHIRPS rainfall):** Precipitation driver
- **InSAR Displacement:** Surface elevation change and subsidence monitoring via Sentinel-1 interferometry

## Study Area

**Murnauer Moos**, Bavaria, Germany — one of Central Europe’s largest continuous peatlands. It is an important carbon sink and biodiversity hotspot, making it an ideal case study for eco-hydrological monitoring.

## Data Sources

- Sentinel-1 SAR (C-band, Interferometric Wide swath mode)
- Sentinel-2 Surface Reflectance
- CHIRPS Daily Rainfall
- Sentinel-1 Interferometric Unwrapped Phase (InSAR) products (GeoTIFF `.geo.unw.tif` files)

## Workflow

1. Access datasets using the Google Earth Engine Python API and local InSAR products.
2. Process data:
   - Compute monthly VH/VV ratio from Sentinel-1 SAR.
   - Compute monthly NDVI from Sentinel-2.
   - Aggregate monthly rainfall totals from CHIRPS.
   - Process InSAR displacement data by masking low-coherence pixels, converting phase to displacement (meters), and clipping to peatland boundaries.
3. Extract time series over the peatland area, combining ecohydrological indicators with surface deformation.
4. Visualize results using Python libraries such as Matplotlib and Pandas.
5. Generate displacement animations to illustrate temporal changes in peatland surface elevation.

## Results

- The **VH/VV ratio** increases with higher rainfall, indicating enhanced peat surface wetness.
- As vegetation greenness (NDVI) rises during summer, the VH/VV ratio declines, suggesting canopy growth dampens the radar signal.
- InSAR displacement analysis reveals subtle surface subsidence patterns linked to peatland hydrology and seasonal water table fluctuations.
- Combined multi-sensor time series provide a holistic view of peatland “breathing” dynamics in Murnauer Moos.


## Tools & Libraries

- Python 3.x
- [Google Earth Engine Python API](https://developers.google.com/earth-engine/guides/python_install)
- Rasterio, rioxarray for geospatial raster processing
- Pandas, Matplotlib for data analysis and visualization
- Jupyter Notebook


## Future Work

- Expand InSAR displacement monitoring with advanced processing (e.g., time series analysis with SNAP, MintPy) to better understand peatland surface deformation mechanisms.
- Integrate water table level measurements and hydrological models with displacement and remote sensing data for improved ecohydrological insights.
- Develop carbon flux proxies by linking remote sensing indicators with field CO₂/CH₄ flux data.
- Apply machine learning techniques to combine multi-source datasets for predictive peatland condition mapping and climate impact assessments.

