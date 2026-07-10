# 🍖 Steak 101 — World's Best Steaks Map

An interactive map of the **World's 101 Best Steaks (2026)**. Browse every ranked steak restaurant on a world map, search by name or city, filter by rank or region, and get directions to the exact spot.

100% Vibe Coding based

## ✨ Features

- 🗺️ **Full-screen interactive map** (Leaflet + CARTO Voyager tiles) with all 101 restaurants
- 🏅 **Rank-badge markers** — gold for the Top 10, red for 11–50, cream for 51–101
- 🧲 **Marker clustering** so dense cities (London, Sydney, New York…) stay readable
- 🔍 **Instant search** by restaurant name or city
- 🎛️ **Filter chips** — All 101, Top 10, Top 25, or by continent
- 📋 **Tappable ranking list** — sidebar on desktop, slide-up bottom sheet on mobile
- 📍 **"Find me" button** to jump to your location and see nearby entries
- 🧭 **Directions & Instagram links** in every marker popup (opens Google Maps to the exact address)
- 📱 **Responsive** — designed mobile-first, with a dedicated desktop layout

## 🚀 Getting started

### Just open it

1. Download `worlds-best-steaks-map.html` (or clone this repo).
2. Double-click the file — it opens in your default browser. That's it.

```bash
git clone https://github.com/<your-username>/steak-101-map.git
cd steak-101-map
# open the file directly, or serve it locally:
python3 -m http.server 8000
# then visit http://localhost:8000/worlds-best-steaks-map.html
```

> **Note:** the "Find me" (geolocation) button requires the page to be served over `https://` or opened via `localhost` in some browsers. Everything else works from a plain `file://` open.

- `worlds-best-steaks-map.html` - original version for Windows
- `worlds-best-steaks-map (1).html` - Another Windows version but included each restaurant's signature steak
- `worlds-best-steaks-map-mobile.html` - Similar but with mobile UI
- `worlds-best-steaks-map-mobile.apk` - App in Android

### Install like an app

- **Android (Chrome):** open the page → menu **⋮** → **Add to Home Screen**. It gets its own icon and launches full-screen.
- **Windows (Edge/Chrome):** open the page → menu → **Apps → Install this site as an app** for a standalone window.
- **iOS (Safari):** Share → **Add to Home Screen**.

### Host it online (optional)

Because it's a single static file, you can publish it free with **GitHub Pages**:

1. Push this repo to GitHub.
2. Rename the file to `index.html` (or keep the name and link to it directly).
3. Repo **Settings → Pages → Deploy from a branch** → select `main` / root.
4. Your map is live at `https://<your-username>.github.io/steak-101-map/`.

## 🛠️ Tech stack

| Piece | What it does |
|---|---|
| [Leaflet 1.9](https://leafletjs.com/) | Map rendering and interactions |
| [Leaflet.markercluster](https://github.com/Leaflet/Leaflet.markercluster) | Clusters nearby markers |
| [CARTO Voyager](https://carto.com/basemaps/) basemap | Bright, readable map tiles (© OpenStreetMap contributors) |
| Vanilla HTML/CSS/JS | No framework, no build step |
| Google Fonts (Anton + Inter) | Typography |

All libraries load from CDNs, so the file itself stays tiny.

## 📊 Data

The restaurant list (rank, name, city, region, Instagram handle) lives in a single `R` array near the top of the `<script>` block:

```js
// rank, name, city, region, lat, lng, instagram
const R = [
  [1, "Bleecker", "London", "Europe", 51.5205, -0.0759, "bleeckersteak"],
  ...
];
```

To update the ranking each year, edit this array — nothing else needs to change.

**Accuracy note:** pins are placed at the neighbourhood/city level (the source list publishes cities, not street addresses). Every popup includes a **Directions** button that opens a Google Maps search for the exact venue.

## 🎨 Customizing

- **Colors:** edit the CSS variables in `:root` (`--gold`, `--tomato`, `--cream`, etc.).
- **Map style:** swap the tile URL — e.g. CARTO `dark_all` for dark mode, `light_all`/Positron for minimal, or standard OSM tiles.
- **Rank tiers:** the `tier()` function controls which ranks get which badge color.

## 🍔 Related Projects

See [SUPPORT.md](SUPPORT.md) for other maps in this series.

## 🙏 Credits

- Ranking: [World Best steaks — Our List](https://www.worldbeststeaks.com/our-list)
- Map data: © [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors, tiles by [CARTO](https://carto.com/)

## 📄 License

MIT — do whatever you like, but keep the map tile and data attributions intact. The steak ranking itself belongs to worldbeststeaks.com.
