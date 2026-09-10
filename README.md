# Flood Risk Exposure by Ward — Newcastle upon Tyne

## Overview
Analysed flood risk exposure across Newcastle upon Tyne's 26 electoral wards by
overlaying Environment Agency Flood Zone 2/3 data with ward boundaries and Census
2021 population estimates.

## Method
- Sourced Flood Zone 2/3 polygons from the Environment Agency's Flood Map for
  Planning dataset
- Reprojected all data to British National Grid (EPSG:27700) for accurate area
  calculation
- Used a geometric overlay (gpd.overlay) to calculate the precise intersection
  between each ward and the flood zones
- Computed three complementary metrics per ward:
  - *% of ward area in Flood Zone 2/3* — proportional risk concentration
  - *Absolute flood zone area (m²)* — total exposure regardless of ward size
  - *Flood zone area per 1,000 residents* — exposure relative to population
- Produced a labelled choropleth in Python (geopandas/matplotlib) and a fully
  composed map layout in QGIS

## Key Finding
*Parklands* ward ranks highest across all three metrics — proportionally,
absolutely, and per-population — consistent with drainage/attenuation infrastructure
near the Newcastle Great Park development. Notably, *Castle* ward shows a large
absolute flood zone area but a low percentage, since it's one of the largest wards
by land area — a reminder that absolute and proportional risk metrics can diverge
significantly, and both are needed for a complete picture. Wards along the River
Tyne itself (Ouseburn, South Jesmond) show consistent but smaller exposure across
all three measures.

## Visuals
- newcastle_flood_risk_labeled.png — Python/matplotlib choropleth
- newcastle_flood_risk_qgis.png — QGIS composed map

## Tools
Python (geopandas, pandas, matplotlib), QGIS, Environment Agency & ONS open data
