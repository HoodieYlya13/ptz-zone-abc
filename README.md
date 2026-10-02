# PTZ Zone ABC Map - Grand Est Region

An interactive map to visualize the **ABC Zoning for the Zero-Interest Loan (PTZ - Prêt à Taux Zéro)** across all municipalities in the **Grand Est region**, France (effective as of June 26, 2026).

![Leaflet](https://img.shields.io/badge/Leaflet-1.9.4-green.svg)
![HTML5/JS](https://img.shields.io/badge/Stack-HTML5%20%2F%20JavaScript-blue.svg)

---

## 📌 Overview

This web application allows users to quickly check PTZ eligibility for ~5,100 municipalities across the 10 departments of the Grand Est region:
- **08** (Ardennes)
- **10** (Aube)
- **51** (Marne)
- **52** (Haute-Marne)
- **54** (Meurthe-et-Moselle)
- **55** (Meuse)
- **57** (Moselle)
- **67** (Bas-Rhin)
- **68** (Haut-Rhin)
- **88** (Vosges)

## 🚀 Features

- 🗺️ **Interactive Leaflet Map** centered on the Grand Est region.
- 🎨 **Intuitive Color Scheme**:
  - 🔴 **Zone B1 / A**: Tight housing market (Ineligible for renovated old PTZ, new builds only).
  - 🟡 **Zone B2**: Eligible for renovated old PTZ & new builds.
  - 🟢 **Zone C**: Eligible for renovated old PTZ & new builds.
- 📊 **Information Popups** on click for every municipality (Name, INSEE code, PTZ Zone, and eligibility thresholds).
- ⚡ **Dynamic Data Sync** based on the official CSV file `ptz-zoning.csv` (*ABC Zoning effective as of June 26, 2026*).
- 🌐 **Official Boundaries** dynamically fetched via French Government GeoJSON API ([geo.api.gouv.fr](https://geo.api.gouv.fr/)).

## 📁 Project Structure

```text
.
├── .gitignore   # Git ignore rules
├── index.html   # Main application interface (HTML / CSS / JavaScript)
├── ptz-zoning.csv   # ABC zoning dataset by INSEE commune code
└── README.md    # Project documentation
```

## 🛠️ Setup & Usage

1. **Clone the repository**:
   ```bash
   git clone https://github.com/HoodieYlya13/ptz-zone-abc-grand-est.git
   cd ptz-zone-abc-grand-est
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
- **Municipal Boundaries**: Etalab / geo.api.gouv.fr GeoJSON API.

