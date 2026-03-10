# Streambank_P

Author: Christy Dolph

Updated: March 3, 2026

Contact: dolph008\@umn.edu

# Overview

This repository provides data and R Markdown scripts used in the preparation of Dolph et al., (in review), *"Streambanks are not like other soils: predicting streambank phosphorus content using machine learning".* The repository contains some of the input data used in this analysis (see descriptions below; note that some of the input data is also published in an independent location), as well as a set of R Markdown scripts that provide the following: a summary of soil and streambank phosphorus, methods for assigning geospatial attributes to sampled point locations, and methods for tuning Random Forest and XGBoost machine learning models used to predict soil and streambank total phosphorus. These scripts include code used to produce the figures in the manuscript.

# Set Up & Installation

1.  Download `~/Streambank_P.zip` to local file system.

2.  Unzip the files to a folder labeled `~/Streambank_P`.

3.  Still in the local file system, open the `Streambank_PRproj` file. This will open the project in RStudio and set the working directory to `~/Streambank_P`.

4.  Run the RMarkdown scripts in numerical order, beginning with `Module1_LoadData.Rmd`. Follow the notes in each script file for detailed instructions.

5.  All file paths within the scripts are relative.

# Datasets

These are found in the "Streambank_P_measured_data" directory.

## 1) Modern upland soil total phosphorus data

Upland soil total phosphorus data was compiled from the USGS National Geochemical Survey and the USDA National Soil Characterization Survey (NCSS) and was pre-processed as described by Dolph et al., (2023). This pre-processed data includes data collected between 2000-2010 and is included here in 2 files:

-   "NCSS_alldepths_MajorElements_since2000_region_NLCD06_NHDv2100_NWI_ssurgo_catchment.csv"

-   "USGS_alldepths_soil_since2000_region_NWI_NHDv2100_NLCD06_ssurgo_catchment.csv"

## 2) Streambank phosphorus data

Streambank phosphorus data was collected by Andrew Margenot et al., and is soon to be published in an independent repository in X.

## 3) Historic soil total phosphorus data

Historic soil phosphorus data is from the Illinois Soil Survey and was compiled by Andrew Margenot et al. at the University of Illinois, and is soon to be published in an independent repository in X.

# R Markdown Scripts Used for Analysis

This repository contains the following R Markdown scripts:

-   **"Module1_LoadData.Rmd"**: This script loads, processes and summarizes upland soil (modern and historic) and streambank total phosphorus (TP) data. The script also creates a mapy of the study area and sets the area of interest for module 2, where features (predictors) are assigned to sample locations.

-   **"Module2_Assign_Geospatial_Predictors.Rmd"**: This script includes code for assigning attributes from the National Land Cover Dataset, the National Wetland Inventory, the National Hydrography Dataset, EPA Streamcat and gSSURGO to the soil and streambank sampled locations included in the study.

-   **"Module2.1_Assign_Limited_SSURGO.Rmd"**: This script provides an alternative to Section 6.2 of Module 2, where only some SSURGO predictors are assigned. See notes in script.

-   **"Module3_Tune_Models.Rmd"**: This script includes code for tuning machine learning models (Random Forest, XGBoost) used to predict upland and streambank total phosphorus, and for calculating variable importance using multiple methods (including SHAP values)

# Citations

Dolph, C. L., Cho, S. J., Finlay, J. C., Hansen, A. T., & Dalzell, B. (2023). Predicting high resolution total phosphorus concentrations for soils of the Upper Mississippi River Basin using machine learning. Biogeochemistry, 163(3), 289–310. <https://doi.org/10.1007/s10533-023-01029-8> 
