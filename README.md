# KAZIME

A responsive anime discovery and streaming frontend powered by the unofficial [HiAnime API](https://github.com/ryanwtf7/hianime-api).

## Features

- Trending, popular and recently updated anime sections
- Anime search and genre browsing
- Anime details, synopsis and episode lists
- SUB / DUB selection and available embed-server selection
- Device-local watchlist
- Responsive dark interface for mobile and desktop

## Setup

This repository contains the frontend only. The HiAnime API is a separate service and must be deployed independently.

1. Deploy your own instance of [ryanwtf7/hianime-api](https://github.com/ryanwtf7/hianime-api) using its README instructions.
2. Open the KAZIME website.
3. Select the ⚙ settings button and enter your API origin, for example `https://your-api.example.com` (do not append `/api/v2`).
4. Save. KAZIME will call the API under `/api/v2`.

The API project documents Vercel and Docker deployment. Its local development server uses the port configured by that project.

## Run locally

Because this is a static site, you can serve the repository with any static HTTP server. For example:

```bash
python -m http.server 8080
```

Then open http://localhost:8080 and configure the API URL in settings.

## Deploy frontend with GitHub Pages

1. Open this repository's **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select the `main` branch and `/(root)`, then save.
4. Wait for GitHub Pages to publish the site.
5. Open the published URL and set the deployed API URL in KAZIME settings.

## API routes used

- `GET /api/v2/home`
- `GET /api/v2/search?keyword=...`
- `GET /api/v2/anime/:id`
- `GET /api/v2/episodes/:id`
- `GET /api/v2/servers/:episodeId?type=sub|dub`
- `GET /api/v2/animes/genre/:genre?page=1`
- `GET /api/v2/random`

## Notes

- The API is unofficial and scrapes a third-party anime source. Availability, response formats, streaming servers and embed permissions can change.
- Use this project for personal and lawful access only. Respect copyright and the terms of the content providers.
- Watchlist data is stored in the browser's local storage and is not synced between devices.
