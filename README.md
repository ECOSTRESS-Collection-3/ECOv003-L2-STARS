# ECOSTRESS Level 2 Vegetation Index & Albedo

This is the main repository for the ECOsystem Spaceborne Thermal Radiometer Experiment on Space Station (ECOSTRESS) collection 3 level 2 STARS NDVI and albedo data product. This product will utilize the [Spatial Timeseries for Automated high-Resolution multi-Sensor (STARS)](https://github.com/STARS-Data-Fusion) data fusion system to produce normalized difference vegetation index (NDVI) and albedo estimates corresponding to ECOSTRESS surface temperature measurements, to support the [evapotranspiration product](https://github.com/ECOSTRESS-Collection-3/ECOv003-L3-JET).

The ECOSTRESS collection 3 level 2 vegetation index and albedo data product is the pre-cursor to the [Surface Biology and Geology (SBG) collection 1 level 2 vegetation index and albedo data product algorithm](https://github.com/sbg-tir/SBG-TIR-L2-STARS).

[Gregory H. Halverson](https://github.com/gregory-halverson-jpl) (they/them)<br>
[gregory.h.halverson@jpl.nasa.gov](mailto:gregory.h.halverson@jpl.nasa.gov)<br>
NASA Jet Propulsion Laboratory 329G

[Margaret C. Johnson](https://github.com/majohnso) (she/her)<br>
[maggie.johnson@jpl.nasa.gov](mailto:maggie.johnson@jpl.nasa.gov)<br>
NASA Jet Propulsion Laboratory 398L

[Kerry Cawse-Nicholson](https://github.com/kcawse) (she/her)<br>
[kerry-anne.cawse-nicholson@jpl.nasa.gov](mailto:kerry-anne.cawse-nicholson@jpl.nasa.gov)<br>
NASA Jet Propulsion Laboratory 329G

[Claire Villanueva-Weeks](https://github.com/clairesvw) (she/her)<br>
[claire.s.villanueva-weeks@jpl.nasa.gov](mailto:claire.s.villanueva-weeks@jpl.nasa.gov)<br>
NASA Jet Propulsion Laboratory 329G

The code for the ECOSTRESS level 2 STARS PGE will be developed using open-science practices based on the [ECOSTRESS collection 2 gridded and tiled product generation software](https://github.com/ECOSTRESS-Collection-2/ECOSTRESS-Collection-2).

This software will produce estimates of:
- Normalized Difference Vegetation Index (NDVI)
- albedo

NDVI and albedo are estimated at 70 m ECOSTRESS standard resolution for each daytime ECOSTRESS overpass by fusing temporally sparse but fine spatial resolution images from the Harmonized Landsat Sentinel (HLS) 2.0 product with daily, moderate spatial resolution images from the Suomi NPP Visible Infrared Imaging Radiometer Suite (VIIRS) VNP09GA product. The data fusion is performed using a variant of the Spatial Timeseries for Automated high-Resolution multi-Sensor data fusion (STARS) algorithm developed by Dr. Margaret Johnson and Gregory Halverson at the Jet Propulsion Laboratory. STARS is a Bayesian timeseries methodology that provides streaming data fusion and uncertainty quantification through efficient Kalman filtering.

Operationally, each L2T STARS tile run loads the means and covariances of the STARS model saved from the most recent tile run, then iteratively advances the means and covariances forward each day updating with fine imagery from HLS and/or moderate resolution imagery from VIIRS up to the day of the target SBG overpass. A pixelwise, lagged 16-day implementation of the VNP43 algorithm (Schaaf, 2017) is used for a near-real-time BRDF correction on the VNP09GA products to produce VIIRS NDVI and albedo.

## 1. Introduction to Data Products

The data format for the SBG products is described in the [ECOSTRESS Collection 3 landing page](https://github.com/ECOSTRESS-Collection-3).

