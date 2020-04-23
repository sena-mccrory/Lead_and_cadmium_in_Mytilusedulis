# ENV872_FinalProject


## Summary

This repository contains code and analysis for a time series investigation and comparison of cadmium and lead concentrations in *Mytilus edulis* (blue mussels) by country using environmental monitoring data from several European countries collected between 1979 to 2018. *Mytilus edulis* are commonly used for coastal biomonitoring efforts due to their wide habitat range and their tendency to filter and collect aquatic pollutants, including heavy metals. Monitoring pollutant concentrations in *Mylius edulis* can help provide an indication of overall ecosystem health. Additionally, these bivalves are an important commercially harvested species and so bioaccumulated heavy metals can also be a threat to human health.

## Investigators

Data and anlaysis were prepared by Sena McCrory, a masters student at the Nicholas School of the Environment, Duke University. 

Contact information: sena.mccrory@duke.edu


## Keywords

ICES, marine contaminants, heavy metals, cadmium, biomonitoring, lead, Mytilus edulis, blue mussel

## Database Information

All datasets used in this analysis are publically available.

Biological Contaminants Data:
Data for contaminants in biota was dowloaded from the International Council for the Exploration of the Sea (ICES) DOME database on Feb 26, 2020. This data portal holds a collection of marine related monitoring data sourced from several regional European monitoring groups including ICES, OSPAR, HELCOM, AMAP, and Expert Groups. Data for all metal and metalloid concentrations in biota were downloaded and then filtered for just Mytilus edulis species and the specific heavy metals of interest for this study.The ICES DOME data portal can be accessed here:http://dome.ices.dk/views/ContaminantsBiota.aspx. Geographic locations are given in decimal degrees (WGS84).   

Global Coastline Data: 
Global Self-consistent Hierarchical High-resolution Geography (GSHHG) coastline data was downloaded from the National Oceanographic and Atmospheric Administration's (NOAA) National Center for Environmental Information (NCEI) online data portal located here: https://www.ngdc.noaa.gov/mgg/shorelines/. L1 resolution shapefile was used for study sampling maps in this analysis. Geographic reference system is WGS84 (decimal degrees). 


## Folder structure, file formats, and naming conventions 

* Code: contains all data processing and analysis code
* Data: contains folders for metadata, raw data (tables only), processed data, and spatial data.
* Resources: contains publications and/or reference materials related to the analysis
* Output: contains any maps created durign analysis as well as the final report in Rmarkdown and pdf format. 

File types used in this repository include Rmarkdown documents, .csv, .pdf, and spatial data are stored as ESRI shapefiles, .shp.   

Naming conventions -
* Raw data files have their original names as they were downloaded.
* Processed datasets are named with self explanatory labels. All processed data files are for the study period for Feb 1990 to Jan 2019 except 'ICES_Mytilusedulis_Cd_Pb.csv' which includes the full range of downloaded data from 1979 to 2019.
* Other files use self explanatory names such as "DataAnalysis" or "DataProcessing" where the first letter of each word is capitolized. 

## Metadata

Processed data file "ICES_Mytilusedulis_Cd_Pb_Hg_Cu.csv" column names are described in detail in the metadata file located in /Data/Metadata/DOMEdata/'Contaminants and effects of contaminants in biota.pdf'. Concentration data used in this analyses (Value.mgperkg and DETLI.mgperkg) have been converted to mg/kg.    

Data for all metal and metalloid concentrations in biota were downloaded and then filtered to include only *Mytilus edulis* species and the specific heavy metals of interest for this study. The sampling data for *Mytilus edulis* was restricted to include only concentrations reported for the “whole soft body” of the bivalve and expressed in mass of metal per mass of the organism wet weight. There was no information provided to allow a conversion from dry weight to wet weight concentrations, and so dry weight records (a small minority of the data) were excluded from the analysis. Additionally, records flagged as having “suspect” data quality were excluded from the data set. Dataset variables are described in Table 1 below.    

Key variable names are summarised in the table below: 
\newpage
Table: Variable descriptions and statistics for ICES DOME monitoring data 

Variable name | Description | Statistics for Cd | Statistics for Pb
-------------- | -------------------- | ----------------------- | -----------------------
PARAM | Parameter | "Cd" – cadmium (6762 records) | "Pb" – lead (6709 records)
MYEAR | Monitoring year (may differ from the sampling year, NOT used in temporal trend analysis) | 1990 - 2018 | 1990 - 2018
DATE | Sample date | February 6, 1990 to Feb 27, 2019 | February 6, 1990 to Feb 27, 2019
Latitude and Longitude | units: decimal degrees |  | 
Country | Country where measurement was reported | | 
Value.mgperkg | Concentration of contaminant in subsample. Units: mg metal/kg organism mass (wet weight of whole soft body).  | range DL – 38.9; median 0.18; mean 0.32 | range DL - 98.01; median 0.28; mean 0.01
NOINP | Number of individuals included in the subsample | range 1-703 | range 1-703
DETLI.mgperkg | Reported detection limit of measurement equipment, units in mg/kg | range 0.000007 to 1; 1792 unreported | range 0.0001 - 0.6; 1736 unreported
QFLAG | Quality flag (see DOME metadata for full description of codes) |  24 <; 1  D; 2 Q; 6735 NA | 69 <; 0  D; 5 Q; 6635 NA


## Scripts and code

Main repository folder contains three additional scripts:
* 'README' (this document)
* 'LICENSE' describing the GNU General Pubilic License
* '.gitignore' which contains and files which were not synced to the github repository due to file size constraints (includes the original data download from ICES DOME database). 

## Quality assurance/quality control

ICES DOME data QA/QC: All data flagged as "suspect" data quality were excluded from the analysis. After all necessary filtering was completed, only a few obvious outliers remained in the data. These outliers were retained in the data for statistical analysis, but may not be shown in the visual representations of the data due to scaling issues. 
