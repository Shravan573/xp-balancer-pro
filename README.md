# XP Balancer Pro

Professional game progression design tool for balancing XP curves, comparing progression systems, and exporting data for production use.

## Features

### Progression Calculator
- Configure **XP per match**, **matches per day**, and **max level** (up to 100)
- Instantly view total XP, total matches, days to max, and weeks to max
- Level-by-level breakdown with min/max XP, XP range, cumulative totals, matches, and days

### 5 Progression Curves
| Curve | Description | Parameters |
|-------|-------------|------------|
| **Current** | Your hardcoded XP data (50 levels default) | — |
| **Exponential** | Multiplier-based scaling | Multiplier (default 1.15) |
| **Linear** | Flat XP increase per level | XP Increase (default 1000) |
| **Steep Early** | Power curve, steep at low levels | Base XP, Exponent |
| **Smooth** | Gradual linear ramp | Base XP, Level Factor |
| **Custom** | Write your own JS formula | `level * 1000 + Math.pow(level, 1.5) * 200` |

### Curve Comparison
- Side-by-side table comparing all curve types at every level
- Overlay chart with color-coded lines for each curve

### Industry Benchmarks
Pre-built progression curves modeled after popular games:
- Fortnite Battle Pass (Exponential)
- Apex Legends (Steep Early)
- Call of Duty (Linear)
- League of Legends (Smooth)
- Valorant (Exponential)
- Mobile RPG Standard (Steep Early)

Click any benchmark to load its curve and parameters instantly.

### Google Sheets Export
- **Tab-separated data** — copy and paste directly into Google Sheets
- **Auto-generated Apps Script** — paste into Extensions > Apps Script to create a fully formatted sheet with:
  - Headers, row banding, and frozen rows
  - Number formatting and auto-resized columns
  - Milestone highlighting (every 10 levels)
  - Summary section with curve type, settings, and totals
  - Embedded XP progression chart

### Charts
- **XP Progression Curve** — dual-axis chart showing Total XP and XP per Level
- **All Curves Comparison** — overlay of all 5 curve types

### Additional Tools
- **Light/Dark theme** toggle
- **Undo/Redo** history (up to 50 states)
- **Import** data from CSV or JSON
- **Export** to CSV, JSON, or shareable URL (base64-encoded)
- **Presets** — save and load named curve configurations (localStorage)
- **Copy** individual row data to clipboard
- **Print** support with clean layout

## Usage

Open `index.html` in any modern browser. No build step or server required.

### Quick Start
1. Set your **XP Per Match** and **Matches Per Day** values
2. Choose a **Progression Curve** or load a benchmark
3. Adjust curve parameters to tune the feel
4. Switch between tabs to view tables, charts, and comparisons
5. Export to Google Sheets or download as CSV/JSON

### Custom Formula
Select "Custom Formula" from the curve dropdown and enter any JavaScript expression using `level` as the variable:
```js
Math.pow(level, 2) * 100
level * 1000 + Math.pow(level, 1.5) * 200
```

### Sharing
Use **Export > Share URL** to generate a link that encodes your current settings. Anyone opening the link will see your exact curve configuration.

## Tech Stack

- **HTML/CSS/JS** — single-file, no dependencies beyond Chart.js
- **Chart.js** (CDN) — for all data visualizations
- **localStorage** — for persisting saved presets

## Author

Created by [Shravan Kumar KS](https://www.linkedin.com/in/shravankumarks/)
