# Streambank_P

Author: Christy Dolph

Updated: March 3, 2026

Contact: dolph008\@umn.edu

# Overview

This repository provides data and R Markdown scripts used in the preparation of Dolph et al., (in review), *"Streambank soils are not like other soils: evaluating modeling approaches to predict streambank phosphorus".* The repository contains some of the input data used in this analysis (see descriptions below; note that some of the input data is also published in an independent location), as well as a set of R Markdown scripts that provide the following: a summary of soil and streambank phosphorus, methods for assigning geospatial attributes to sampled point locations, and methods for creating and evaluating models used to predict soil and streambank total phosphorus (including random forest, XGBoost, LASSO, generalized linear model, linear model). These scripts include code used to produce the figures in the manuscript. We also publish a dataset of predicted streambank TP for streambanks in Illinois at the 30m scale, based on the best available predictive model. Predictions are available for streambank depths of 104 cm, 175 cm and 260 cm. While the predicted values are more accurate than using a mean of streambank TP as a prediction for all sites in Illinois, even the best available model shows considerable room for improvement, so these predictions should be interpreted carefully/with a grain of salt.

# Set Up & Installation

1.  Download `~/Streambank_P.zip` to local file system.

2.  Unzip the files to a folder labeled `~/Streambank_P`.

3.  Still in the local file system, open the `Streambank_PRproj` file. This will open the project in RStudio and set the working directory to `~/Streambank_P`.

4.  Run the RMarkdown scripts in numerical order, beginning with `Module1_LoadData.Rmd`. Follow the notes in each script file for detailed instructions.

5.  All file paths within the scripts are relative.

# Datasets

These are found in the "Streambank_P_measured_data" directory.

## 1) Soil total phosphorus data from the Midwestern U.S.

Soil total phosphorus data (7,093 soil samples collected at 3,179 unique sites) was compiled for 12 states from the broadly defined Midwestern U.S. (Arkansas, Iowa, Illinois, Indiana, Kansas, Minnesota, Missouri, North Dakota, Nebraska, Ohio, South Dakota, and Wisconsin). Data was from the USGS National Geochemical Survey and the USDA National Soil Characterization Survey (NCSS) and was pre-processed as described by Dolph et al., (2023). Most of these samples were from upland environments (a minority were from riparian environments). The original datasets were accesssed from:

- USGS National Geochemical Survey: <https://mrdata.usgs.gov/geochem/>)

- USDA: National Cooperative Soil Survey (NCSS) Characterization Dataset: <https://ncsslabdatamart.sc.egov.usda.gov/>).

Pre-processed data associated with the current repository includes data collected between 2000-2010 and is included here in 2 files:

- "NCSS_alldepths_MajorElements_since2000_region_NLCD06_NHDv2100_NWI_ssurgo_catchment.csv"

- "USGS_alldepths_soil_since2000_region_NWI_NHDv2100_NLCD06_ssurgo_catchment.csv"

## 2) Streambank phosphorus data

Streambank phosphorus data was collected by Andrew Margenot et al., and is soon to be published in an independent repository.

# R Markdown Scripts Used for Analysis

This repository contains the following R Markdown scripts:

- **"Module1_LoadData.Rmd"**: This script loads, processes and summarizes upland soil (modern and historic) and streambank total phosphorus (TP) data. The script also creates a mapy of the study area and sets the area of interest for module 2, where features (predictors) are assigned to sample locations.

- **"Module2_Assign_Geospatial_Predictors.Rmd"**: This script includes code for assigning attributes from the National Land Cover Dataset, the National Wetland Inventory, the National Hydrography Dataset, EPA Streamcat and gSSURGO to the soil and streambank sampled locations included in the study.

- **"Module2.1_Assign_Limited_SSURGO.Rmd"**: This script provides an alternative to Section 6.2 of Module 2, where only some SSURGO predictors are assigned. See notes in script.

- **"Module3_Compare_streambank_vs_Midwest_TP.Rmd"**: This script compares TP as well as other geospatial predictors between streambank and Midwest datasets.

- **"Module4_Tune_Models.Rmd"**: This script includes code for evaluating models (including random forest, XGBoost, LASSO, glm, lm) used to predict Midwest and streambank total phosphorus, and for calculating variable importance using multiple methods (including SHAP values)

- **"Module5_Predict_StreambankTP"**: This script includes code for using the best available streambank TP model to predict TP values at 3 depths for streambanks across Illinois at 30m scale.

# Citations

Dolph, C. L., Cho, S. J., Finlay, J. C., Hansen, A. T., & Dalzell, B. (2023). Predicting high resolution total phosphorus concentrations for soils of the Upper Mississippi River Basin using machine learning. Biogeochemistry, 163(3), 289–310. <https://doi.org/10.1007/s10533-023-01029-8> 
