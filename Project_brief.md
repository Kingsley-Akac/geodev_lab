# Project Brief — Week 1

## Spatial Question
Which residential areas across Port Harcourt and Obio/Akpor Local Government Areas (LGAs), Rivers State, Nigeria, sit closest to drainage channels and in the lowest-elevation zones — putting them at greater flood risk — and which specific neighborhoods should be prioritized for drainage improvement?

## Study Area
Port Harcourt LGA and Obio/Akpor LGA, Rivers State, Nigeria. These two adjoining LGAs make up the core of the Port Harcourt metropolitan area and are the LGAs most consistently referenced in flood research on the city, with Obio/Akpor repeatedly identified as the more severely affected of the two.

## Background / Justification
Port Harcourt experiences flooding in most rainy seasons, driven by a combination of low elevation, inadequate drainage infrastructure, and rapid, largely unplanned urban development. Independent studies on the metropolis point to a consistent pattern: streets in Obio/Akpor LGA are disproportionately affected compared to Port Harcourt LGA proper. This project uses open geospatial data to test whether a simple elevation-plus-drainage-proximity model reproduces that known pattern, and to identify specific neighborhoods that would most benefit from drainage investment.

## Datasets

| # | Dataset | Format / Type | Source (link) |
|---|---|---|---|
| 1 | Waterways & drainage (rivers, streams, drains, water bodies) | OSM vector (lines/polygons), via QuickOSM in QGIS | https://www.openstreetmap.org |
| 2 | Residential buildings | OSM vector (polygons), via QuickOSM in QGIS | https://www.openstreetmap.org |
| 3 | Digital Elevation Model (SRTM, 30m) | Raster | https://earthexplorer.usgs.gov |
| 4 | Administrative boundaries — Admin 2 / LGA level (Port Harcourt & Obio/Akpor) | Vector (polygon) | https://data.humdata.org/dataset/cod-ab-nga |
| 5 *(optional, for validation)* | Historical flood-affected areas by LGA, 2022 (NEMA) | Vector (polygon) / CSV | https://data.humdata.org/dataset/nigeria-nema-flood-affected-geographical-areasnorth-east-nigeria-flood-affected-geographical-areas |

## Planned Method (brief)
1. Clip OSM waterways, buildings, and the SRTM DEM to the combined Port Harcourt + Obio/Akpor boundary.
2. Buffer waterways to flag buildings within a defined proximity to drainage channels.
3. Reclassify the DEM to flag low-elevation zones.
4. Overlay proximity and elevation flags to identify buildings/areas of highest exposure.
5. Compare results between the two LGAs to check whether Obio/Akpor shows higher exposure, consistent with existing research — a built-in sanity check on the method.

## Expected Output
A map and short write-up identifying the residential neighborhoods within Port Harcourt and Obio/Akpor at highest flood exposure, ranked by combined elevation and drainage-proximity risk.
