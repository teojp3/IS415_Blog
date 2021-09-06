---
title: "Take Home Exercise 1"
description: |
  Analysing and Visualising Spatio-temporal Patterns of COVID-19 in DKI Jakarta, Indonesia.
author:
  - name: Teo Jun Peng
    url: https://teojp3-is415.netlify.app/
date: 08-27-2021
output:
  distill::distill_article:
    self_contained: false
---




# 1. Introduction

This analysis aims to analyse and visualise spatio-temporal patterns of COVID-19 in DKI Jakarta, Indonesia. Out of 34 provinces in Indonesia, DKI Jakarta was the province affected most by the pandemic, with close to 24% of cumulative confirmed cases. However, the cumulative confirmed cases were not evenly distributed, therefore this analysis intends to unravel which sub-districts had the highest number of cases and how time has changed the overall distribution.

## THE DATA

For this analysis, the following data are used:

- [Open Data Covid-19 Provinsi DKI Jakarta](https://riwayat-file-covid-19-dki-jakarta-jakartagis.hub.arcgis.com/). This portal provides daily update of COVID-19 measures at both sub-district and district level. For the purpose of this analysis, data at the sub-district level is used. The datasets are in .CSV format, and monthly datasets from March 2020 to July 2021 will be used.

- [Indonesia Geospatial](https://www.indonesia-geospasial.com/). This portal provides a comprehensive collection of geospatial data mainly in ESRI shapefile format at different geographical levels. For the purpose of this analysis, the Shapefile (SHP) Batas Desa Provinsi DKI Jakarta provided at PODES 2019 geospatial layer is used.

# 2. Setting up the environment

- R packages will be used for efficiency and a more comprehensive analysis, such as *tidyverse* and *sf* etc.


```r
load("THE1_workspace.Rdata")
packages = c('tidyverse', 'sf', 'readxl', 'readr', 'stringr', 'tmap')
for (p in packages)
  {
  if(!require(p, character.only = T))
    {
    install.packages(p)
  }
  library(p,character.only = T)
}
```
# Prevent values from showing as exponential

























































































































