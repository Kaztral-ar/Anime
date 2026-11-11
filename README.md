# KAZIME

A responsive anime discovery website powered directly by the public [AniList GraphQL API](https://docs.anilist.co/). No API key, backend deployment, or manual API URL configuration is required.

## Features

- Trending, popular, and recently updated anime
- Anime search and genre browsing
- Anime details, synopsis, scores, and episode counts
- Device-local watchlist
- Watch buttons that open availability searches on JustWatch India and official anime channel searches on YouTube
- Responsive dark interface for mobile and desktop

## Run locally

This is a static website. Serve the repository with any static HTTP server:

```bash
python -m http.server 8080
```

Then open http://localhost:8080.

## API

KAZIME sends public GraphQL requests directly to `https://graphql.anilist.co`. Public anime metadata does not require AniList authentication. See the [official AniList API documentation](https://docs.anilist.co/guide/graphql/).

## Watching anime

AniList provides anime metadata; it does not provide video streams or episode playback. The **Watch now** action opens:
- [JustWatch India](https://www.justwatch.com/in/) to check licensed streaming availability.
- YouTube search for official anime distributors and channels such as Muse Asia and Ani-One.

Availability depends on region and provider subscriptions. KAZIME does not host, proxy, or embed copyrighted video.

## Deploy with GitHub Pages

1. Open **Settings → Pages** in this repository.
2. Choose **Deploy from a branch**.
3. Select `main` and `/(root)`, then save.
4. Open the published GitHub Pages URL. The site connects to AniList automatically.

## Notes

- AniList API availability and rate limits are controlled by AniList.
- Watchlist entries are stored in browser local storage and are not synced between devices.
