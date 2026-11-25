# FishDex

A personal fishing life list, catch log and photo gallery in one browser file.

**[Open FishDex](https://michaelaperry.github.io/FishDex/)** or download
[`index.html`](index.html) to run it locally. Entries stay in the browser
where you record them. Export a backup before resetting browser data or switching devices.

Built with assistance from Claude.

## What It Does

FishDex is a zero-dependency, single-file web app for anglers who want to track every species they've ever caught. Think of it like a Pokédex — but for fish.

| View | What's in it |
|------|-------------|
| **Dashboard** | Live stats, personal bests per species, recent catches |
| **Life List** | All 92 N. American species as a grid — checked off as you catch them |
| **Log** | Full sortable/filterable catch table with every detail |
| **Gallery** | Photo wall of your catches with full slideshow mode |
| **Map** | Leaflet map — drop pins with coordinates, markers sized by catch count |
| **Stats** | Charts: catches by species, month, location, and lure type |

---

## Features

- 📷 **Photos** — attach via URL or upload a file (stored as base64 in the browser)
- 🎞️ **Slideshow** — full-screen photo slideshow with auto-play, keyboard nav, and dot indicators
- 🗺️ **Map** — interactive dark map, grouped markers, species popups
- 🐟 **92 species** on the master life list, organized by family
- ➕ **Add custom species** — anything not on the list, saved permanently
- 🔍 **Cross-search** the log by species, location, state, lure, notes — anything
- 📊 **Live charts** that update as you log catches
- 💾 **IndexedDB storage** — data lives in your browser, survives refreshes
- ↓↑ **JSON export / import** — back up your data or move it between devices

---

## Deploy in 2 Minutes

This is a single `index.html` file. GitHub Pages will serve it for free.

```bash
# 1. Clone or create your repo
git clone https://github.com/yourusername/fishdex
cd fishdex

# 2. Drop in the file
cp path/to/index.html .

# 3. Push
git add index.html
git commit -m "🎣 Initial FishDex deploy"
git push
```

Then in your repo: **Settings → Pages → Source: `main` branch, `/ (root)` → Save**

Your FishDex will be live at:
```
https://yourusername.github.io/fishdex
```

---

## Data & Privacy

All your data stays **in your browser** (IndexedDB). Nothing is sent to any server. Ever.

- To back up: use the **↓ Export** button on the Dashboard — saves a `.json` file
- To restore or move to another device: use **↑ Import** on the Dashboard
- Base64-embedded photos are not included in exports (too large) — URL-linked photos are

---

## Customizing

The entire app is one HTML file. Open it in any text editor.

**Add a new log field** (e.g. water temperature):
1. Add an `<input>` in the form grid inside `#modal-add`
2. Add `water_temp: get('f-watertemp'),` in `submitCatch()`
3. Add a `<th>` / `<td>` in `renderLog()`

**Add species to the master list:**
The `SPECIES_LIST` constant is near the top of the `<script>` tag. Or use the **+ Add Species** button in the app — no code needed.

**Change the color scheme:**
All colors are CSS variables at the top of the `<style>` tag under `:root { }`.

---

## Stack

| Thing | What |
|-------|------|
| Storage | [IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API) (browser-native) |
| Maps | [Leaflet.js](https://leafletjs.com) + CartoDB dark tiles |
| Charts | [Chart.js](https://www.chartjs.org) |
| Fonts | [Playfair Display](https://fonts.google.com/specimen/Playfair+Display) + [IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Mono) + [Lora](https://fonts.google.com/specimen/Lora) via Google Fonts |
| Everything else | Vanilla JS, HTML, CSS — no build step, no npm, no framework |

---

## Species List Coverage

The master list includes 92 commonly targeted North American freshwater species across:

- Bass (Largemouth, Smallmouth, Spotted, Striped, White, and more)
- Sunfish & Crappie (10 species)
- Pike, Pickerel & Muskie family
- Perch & Walleye
- Trout & Salmon (15 species including steelhead and landlocked)
- Catfish & Bullheads (7 species)
- Carp & Buffalo
- Suckers & Redhorse
- Gar (all 4 species)
- Drum, Bowfin, Eel, Shad, Sturgeon, Paddlefish, and more

Don't see your fish? Hit **+ Add Species** on the Life List.

---

## Contributing

PRs welcome. This was vibe coded — there's plenty of room to make it better.

Ideas welcome for:
- More species (saltwater? Canadian North?)
- Weather / moon phase logging
- Trip/session grouping
- Export to CSV / Excel
- PWA / offline-first mode

---

## License

MIT — do whatever you want with it. Tight lines. 🎣
