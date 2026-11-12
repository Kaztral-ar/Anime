# KAZIME

A responsive anime discovery website using the same HiAnime provider endpoints implemented in [Kaztral-ar/ani-watch](https://github.com/Kaztral-ar/ani-watch).

## Features

- HiAnime search
- Anime detail pages and poster extraction
- Episode lists from the HiAnime episode-list endpoint
- SUB/DUB server listings
- Watchlist saved in browser local storage
- Responsive dark interface

## HiAnime integration

KAZIME uses the provider base URL and routes from AniWatch's `lib/aniwatch/provider_hianime.sh`:

- `https://hianime.at/search?keyword=...`
- `https://hianime.at/api/theme/episode/list/{anime-slug}`
- `https://hianime.at/api/theme/episode/servers?episodeId={episode-id}`

No AniList, Tenrai, API key, or manual API URL setting is used.

## Important browser limitation

AniWatch is a POSIX shell application and makes provider requests with `curl`. KAZIME is a static browser website, so its requests are subject to browser CORS rules. If HiAnime does not allow requests from the GitHub Pages origin, search and episode requests will be blocked by the browser. In that case, a small server-side proxy (for example, a Cloudflare Worker) is required; changing frontend JavaScript cannot bypass CORS.

The AniWatch provider currently extracts search results, episode IDs, and server labels. A server entry may expose only an opaque ID rather than a direct media URL. KAZIME therefore opens the HiAnime episode page when no direct URL is supplied; it does not claim that every listed server can be embedded or played directly.

HiAnime is an unofficial provider integration. Its endpoints and markup can change. Use provider content in accordance with applicable laws and terms.

## Run locally

Serve the repository root with any static HTTP server:

```bash
python -m http.server 8080
```

Then open http://localhost:8080.

## Deploy with GitHub Pages

1. Open **Settings → Pages**.
2. Select **Deploy from a branch**.
3. Choose `main` and `/(root)`, then save.

## Local data

Watchlist entries are stored in browser local storage and are not synced between devices.
