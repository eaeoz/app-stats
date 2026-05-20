# app-stats

Application statistics dashboard — JSON-based, powered by GitHub Actions.

## Overview

This repository automatically collects metrics from various sources via scheduled GitHub Actions workflows. The raw data is stored as JSON files and can be served as a lightweight stats API or rendered into a dashboard.

## How it works

1. GitHub Actions workflows run on a schedule (or on demand) to fetch data from configured sources.
2. The fetched data is processed and written to `data/*.json`.
3. The JSON files can be consumed by a frontend dashboard, used in a GitHub Pages site, or consumed by external tools.

## Usage

```bash
git clone https://github.com/<user>/app-stats
cd app-stats
```

### Local development

If a frontend is included:

```bash
npm install
npm run dev
```

## Project structure

```
.
├── .github/workflows/   # GitHub Actions workflow definitions
├── data/                # Generated JSON stats files (committed by CI)
├── src/                 # Frontend source (if applicable)
└── ...
```

## License

MIT
