# Data Note

## Dataset 1: Places of Worship

* **Source:** OpenStreetMap, via QuickOSM (`amenity=place\_of\_worship`) — https://www.openstreetmap.org
* **Feature count:** \[95]
* **Geometry type:** Point
* **Key columns:** `name`, `amenity`, `religion`, `denomination`, `address street` 
* **Gaps/missing values noticed:** \[`operator`, `service time`, `contact`, `phone`, `opening hours`, `name`; `religion`/`denomination` missing on most points"]

## Dataset 2: Buildings

* **Source:** OpenStreetMap, via QuickOSM (`building=\*`) — https://www.openstreetmap.org
* **Feature count:** \[158,077]
* **Geometry type:** Polygon / Multipolygon
* **Key columns:** `building`, `name`, `addr:city`
* **Gaps/missing values noticed:** \["most features are `building=yes` with no specific subtype"]

## Dataset 3: Administrative Boundaries (LGA \& Ward)

* **Source:** Office of Surveyor General
* **Feature count:** [2 LGA features selected (Port Harcourt, Obio/Akpor)]
* **Geometry type:** Polygon
* **Key columns:** `NAME`, `SHAPE\_LENGHT`, `AREA`
* **Gaps/missing values noticed:** \[NONE]

