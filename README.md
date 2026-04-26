# BC LKI Landmark Explorer

A single-file HTML map viewer for the British Columbia **Landmark Kilometre Inventory (LKI)** — the dataset the BC Ministry of Transportation maintains for identifying locations on the provincial highway network.

## What is the LKI?

The Landmark Kilometre Inventory is one of the systems used by the BC Ministry of Transportation to identify locations on the provincial highway network. It has been in continuous use since before 1978. Police use LKI codes when reporting crash locations on provincial highways.

The inventory divides the highway network into segments, each with a four-digit identifier and designated start and end points. Landmarks (intersections, bridges, ferries, rest areas, etc.) along each segment are listed with their measured kilometre distance from the start of the segment and a numeric type code.

This repository contains the **July 2025 release** (version `202507`) loaded into a self-contained interactive map.

## What's in this repository

- **`index.html`** — the entire application: HTML, CSS, JavaScript, and the embedded landmark dataset in one ~2.7 MB file. No build step. No backend.
- **`LICENSE`** — MIT.

## Running it

Open `index.html` in any modern browser. It needs a network connection to fetch:

- Leaflet 1.9.4 + Leaflet.markercluster 1.5.3 from cdnjs
- Basemap tiles from CARTO (Voyager / Positron) and Esri (World Imagery)

There is no install step, no server, and no API keys.

## Features

- Three basemaps: **Street** (CARTO Voyager), **Light** (CARTO Positron), **Satellite** (Esri World Imagery)
- Filter landmarks by **region**, **highway**, **category**, or by **search** of the description text
- **Filters / List** sidebar toggle — list view shows currently-visible landmarks sorted by description, highway+km, region, or type
- **Click anywhere on the map** to find the nearest landmark (within active filters) and its great-circle distance
- **Region overlay** toggle draws convex-hull polygons around each MOT region
- **About** dialog (info icon in header, or `?` key) explaining the LKI and citing the data source
- Each landmark popup links to **Google Street View** and **Google Maps**, and offers **Copy coords** + **Copy share link** buttons
- Filter, basemap, mode, search, and map view are persisted in the **URL hash** — refresh-safe and shareable
- Search matches are highlighted in popup descriptions and list rows

## Keyboard shortcuts

| Key | Action |
| --- | --- |
| <kbd>/</kbd> | Focus the search field |
| <kbd>1</kbd> <kbd>2</kbd> <kbd>3</kbd> | Switch Street / Light / Satellite basemaps |
| <kbd>L</kbd> | Toggle Filters / List sidebar mode |
| <kbd>?</kbd> | Open the About dialog |
| <kbd>Esc</kbd> | Close popup or modal |

## Categories

Landmark type codes are grouped into 13 categories displayed in the sidebar:

Points of Interest · Structures · Intersections · Rail Crossings · Ferries & Scales · Access · Signs · Lane Changes · Pullouts · Boundaries · Traffic Monitoring · Hazards · Admin

Counts are computed at runtime from the embedded dataset.

## Data source

- BC Ministry of Transportation — [Landmark Kilometre Inventory page](https://www2.gov.bc.ca/gov/content/transportation/transportation-infrastructure/engineering-standards-guidelines/landmark-kilometre-inventory)
- [BC Data Catalogue listing](https://catalogue.data.gov.bc.ca/dataset/ministry-of-transportation-mot-landmark-kilometre-inventory-lki)
- [Open Government Portal listing](https://open.canada.ca/data/en/dataset/2e682dc5-1949-4f82-aa88-ccd96917a056)
- Dataset version: **202507** (July 2025)

## Built with

- [Leaflet](https://leafletjs.com/) 1.9.4
- [Leaflet.markercluster](https://github.com/Leaflet/Leaflet.markercluster) 1.5.3
- Basemap tiles by [CARTO](https://carto.com/) and [Esri](https://www.esri.com/)

## License

MIT — see [LICENSE](LICENSE).
