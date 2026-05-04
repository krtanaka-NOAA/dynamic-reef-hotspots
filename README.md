# dynamic-reef-hotspots
This repository contains the data processing, Species Distribution Modeling (SDM), and spatial analysis pipeline for: "Persisting, emerging, and contracting: The dynamic nature of non-native hotspots and their implications for management."
# Non-native reef fish hotspots

### Persisting, emerging, and contracting: The dynamic nature of non-native hotspots and their implications for management

**Authors:** Laura Gajdzik* and Kisei R. Tanaka* **Correspondence:** kisei.tanaka@noaa.gov  
*\*Contributed equally*

---

## Overview
This repository contains the analytical pipeline for modeling the spatial dynamics of non-native reef fish in the Main Hawaiian Islands (MHI). It integrates GBIF/OBIS data with Bio-Oracle environmental predictors to identify habitat suitability and richness hotspots through 2100.

## Repository Structure
* **1.Occurrence_Cleaning.R**: Data acquisition, filtering, and DBSCAN core-range clustering.
* **2.Prep_Environmental_Layers.R**: VIF analysis and terra-based raster processing for baseline/future layers.
* **3.MaxEnt_Modeling.R**: Ensemble Maxnet modeling (top 5 models by AICc).
* **4.Hotspot_Analysis.R**: Calculation of Getis-Ord Gi* spatial statistics for richness hotspots.
* **GBIF_SDM_Functions.R**: Core functions for modeling and spatial analysis.

## Key Methodologies
- **DBSCAN:** Used to identify 50% and 80% core ranges to handle sampling bias.
- **Ensemble MaxEnt:** Predictions based on the mean of the top 5 models.
- **Gi* Statistics:** Statistically significant hotspot identification (z-score > 2.58).

## Data Access
Raw environmental rasters should be sourced directly from [Bio-Oracle](https://bio-oracle.org/). Bounding boxes and cleaning masks are provided in the `data/` folder.

## License
MIT License
