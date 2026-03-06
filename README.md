# ISU World Allround Championships 2026 — Live Dashboard

**Thialf · Heerenveen · 7–8 March 2026**

## Overview

Live dashboard for the ISU World Allround Championships. Displays real-time results, standings, start lists, and pair comparisons using data from the ISU Results API.

## Features

### Overview Page (4-tile layout)
- **① Live Results** — Current distance results sorted by time, with TR/PB badges
- **② Live Standings** — Real-time overall allround championship standings
- **③ Start List** — Start list with lane indicators (🔴 outer / ⚪ inner) and target time for P1
- **④ Frozen Standings** — Standings snapshot, manually updateable via button. Shows target times for next distance

### Interactions
- **Click athlete name** → Popup with all tournament results, records, and PB per distance
- **Click pair/rit number** → Pair comparison popup with head-to-head results, point difference, and time equivalent
- **Distance selector** → Controls which distance tile 1 & 3 show

### Additional Pages
- **Individual distance views** — Full results + sidebar standings with target times
- **Full Standings** — Complete klassement with all distance times and medals

## Allround Format

**Women:** 500m → 3000m → 1500m → 5000m
**Men:** 500m → 5000m → 1500m → 10.000m

**Points** = time(seconds) ÷ distance factor:

| Distance | Factor |
|----------|--------|
| 500m | 1 |
| 1500m | 3 |
| 3000m | 6 |
| 5000m | 10 |
| 10.000m | 20 |

## Data Source

- Primary: `api.isuresults.eu` (JSON API)
- Fallback 1: allorigins proxy
- Fallback 2: Jina Reader (text parsing)
- Poll interval: 3 seconds

## Configuration

In `app.js`, line 5:
```js
const EVENT_ID = "2024_GER_0001";  // Change to "2026_NED_0002" for live event
```

## Competition IDs (within event)

| # | Distance |
|---|----------|
| 9 | 500m Women |
| 10 | 500m Men |
| 11 | 3000m Women |
| 12 | 5000m Men |
| 13 | 1500m Women |
| 14 | 1500m Men |
| 15 | 5000m Women |
| 16 | 10.000m Men |

## Deployment

Static files — deploy to any web server or open `index.html` directly. No build step required.

## Files

- `index.html` — Page structure
- `app.js` — Application logic, data fetching, rendering
- `styles.css` — ISU-styled dark theme
