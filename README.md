# PTZ Zone ABC Map - France

An interactive map to visualize the **ABC Zoning for the Zero-Interest Loan (PTZ - Prêt à Taux Zéro)** across all municipalities in **France**, metropolitan and overseas (effective as of June 26, 2026).

![Leaflet](https://img.shields.io/badge/Leaflet-1.9.4-green.svg)
![HTML5/JS](https://img.shields.io/badge/Stack-HTML5%20%2F%20JavaScript-blue.svg)

---

## 📌 Overview

This web application allows users to quickly check PTZ eligibility for the ~34,900 municipalities of France, across the 13 metropolitan regions and the 5 overseas regions (Guadeloupe, Martinique, Guyane, La Réunion, Mayotte).

Drawing every commune of France at once is too heavy for a browser, so the map is loaded **region by region**: the app opens on a national view of the regions, and the detailed commune boundaries are only downloaded for the region you select.

## 🚀 Features

- 🗺️ **Interactive Leaflet Map** opening on a national view of the French regions.
- 🧭 **Region-by-region loading**: click a region on the map or pick it from the list (overseas regions included) to load its communes.
- 🔗 **Shareable links**: the selected region is kept in the URL (`#region=44` for Grand Est, for example).
- ⚡ **In-memory cache**: a region already opened reloads instantly.
- 🎨 **Intuitive Color Scheme**:
  - 🔴 **Zone A bis / A / B1**: Tight housing market (PTZ for new builds only).
  - 🟡 **Zone B2**: PTZ for new builds & older homes with renovation work.
  - 🟢 **Zone C**: PTZ for new builds & older homes with renovation work.
- 📊 **Information Popups** on click for every municipality (Name, INSEE code, PTZ Zone, and eligibility).
- 📄 **Dynamic Data Sync** based on the official CSV file `ptz-zoning.csv` (*ABC Zoning effective as of June 26, 2026*).
- 🌐 **Official Boundaries** dynamically fetched via French Government GeoJSON API ([geo.api.gouv.fr](https://geo.api.gouv.fr/)).

## 📁 Project Structure

```text
.
├── .gitignore       # Git ignore rules
├── favicon.ico      # Website favicon icon
├── index.html       # Main application interface (HTML / CSS / JavaScript)
├── portfolio.json   # Project description consumed by my portfolio website
├── ptz-zoning.csv   # ABC zoning dataset by INSEE commune code
└── README.md        # Project documentation
```

## 🛠️ Setup & Usage

1. **Clone the repository**:
   ```bash
   git clone https://github.com/HoodieYlya13/ptz-zone-abc.git
   cd ptz-zone-abc
   ```

2. **Run the application**:
   Since the app performs local `fetch` requests to parse `ptz-zoning.csv`, it is recommended to serve it using a local HTTP server:

   *Using Python 3:*
   ```bash
   python3 -m http.server 8000
   ```
   Then open [http://localhost:8000](http://localhost:8000) in your browser.

## 📄 Data Sources

- **ABC Zoning Data**: Official dataset effective as of June 26, 2026 (`ptz-zoning.csv`).
- **Municipal Boundaries & Regions**: Etalab / geo.api.gouv.fr GeoJSON API.
- **Region Outlines**: [gregoiredavid/france-geojson](https://github.com/gregoiredavid/france-geojson) (simplified version).
