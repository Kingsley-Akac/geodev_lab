# Project Brief — Week 1

## Spatial Question
How are places of worship (churches, mosques, and other religious facilities) distributed across the wards of Port Harcourt and Obio/Akpor LGAs, Rivers State, Nigeria, relative to residential building density — are some wards oversupplied with closely-clustered facilities while others have relatively few for their number of residents?

## Study Area
Port Harcourt LGA and Obio/Akpor LGA, Rivers State, Nigeria — broken down at the ward level (Admin 3) for a more meaningful comparison than just two large LGAs.

## Background / Justification
Port Harcourt has grown rapidly and unevenly, with some suburbs (particularly in Obio/Akpor) expanding faster than formal planning has kept pace. Community facilities like places of worship tend to follow settlement patterns unevenly — clustering heavily in some neighborhoods while remaining sparse in newer or less-developed ones. This project uses open geospatial data to map that distribution at ward level and produce a simple, reusable tool for exploring facility access by location.

## What We're Building
A lightweight **"Nearest Place of Worship" finder** — a single-page map where a user clicks any point in Port Harcourt/Obio-Akpor and instantly sees the nearest place of worship and its distance, plus how many exist within a 1 km radius. Because this only needs point-to-point distance on a small dataset, it can run entirely in the browser:
1. Export the QGIS places-of-worship layer as GeoJSON.
2. Build a single HTML page using Leaflet (for the map) and Turf.js (for distance calculations) — no backend server required.
3. On click, the page finds the nearest point in the GeoJSON and displays its name and distance.

This keeps the "build" piece simple and fully achievable without needing to stand up an API.

## Datasets

| # | Dataset | Format / Type | Source (link) |
|---|---|---|---|
| 1 | Places of worship (churches, mosques, etc.) | OSM vector (points), via QuickOSM in QGIS — `amenity=place_of_worship` | https://www.openstreetmap.org |
| 2 | Residential buildings (density proxy) | OSM vector (polygons), via QuickOSM in QGIS — `building=*` | https://www.openstreetmap.org |
| 3 | Administrative boundaries — Admin 2 (LGA) and Admin 3 (ward) levels | Vector (polygon) | https://data.humdata.org/dataset/cod-ab-nga |

## Planned Method (brief)
1. Download Admin 2 boundaries, select Port Harcourt and Obio/Akpor, and use them to select the wards (Admin 3) that fall inside these two LGAs.
2. Pull places-of-worship points and building footprints via QuickOSM, clipped to the combined ward area.
3. Use **Vector → Analysis Tools → Count Points in Polygon** to get the number of places of worship per ward, and again for buildings, to get a simple facilities-per-building ratio for each ward.
4. Use **Vector → Analysis Tools → Distance to Nearest Hub (points)** to calculate, for each building, the distance to the nearest place of worship — then average this per ward as a simple access metric.
5. Map both the ratio and the average distance by ward to see which areas are relatively over- or under-served.

## Expected Output
A ward-level map showing places-of-worship density and average access distance across Port Harcourt and Obio/Akpor, plus a working "Nearest Place of Worship" browser tool built on the same data.
