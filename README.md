# app-stats

Multi-repo release index — JSON-based, powered by GitHub Actions.

## Overview

Fetches release data from multiple repositories via the GitHub API every 30 minutes and writes a combined index to `public/releases.json`.

## Tracked repositories

- [youtube-downloader](https://github.com/eaeoz/youtube-downloader)
- [movie-downloader](https://github.com/eaeoz/movie-downloader)
- [music-downloader](https://github.com/eaeoz/music-downloader)
- [command-manager-docker](https://github.com/eaeoz/command-manager-docker)
- [sondakika](https://github.com/eaeoz/sondakika)

## Output format

The resulting `public/releases.json` structure:

```json
{
  "projects": [
    {
      "repo": "youtube-downloader",
      "releases": [
        {
          "tag": "v1.0.0",
          "name": "Initial release",
          "published": "2026-01-01T00:00:00Z",
          "assets": [
            { "name": "app.exe", "downloads": 42 }
          ]
        }
      ]
    }
  ]
}
```

## Usage

```bash
git clone https://github.com/eaeoz/app-stats
cd app-stats
```

The JSON can be consumed by a frontend dashboard, GitHub Pages site, or external tools — hosted at `/public/releases.json`.

## Project structure

```
.
├── .github/workflows/        # GitHub Actions workflow definitions
├── public/                   # Generated release index (committed by CI)
└── README.md
```

## License

MIT
