# Games

Three browser games packaged as installable, offline-capable PWAs.

| Game | Folder |
|---|---|
| Hivefall | `hivefall/` |
| ROGUE AI | `rogue-ai/` |
| Tower Hop | `tower-hop/` |

Each folder is self-contained: `index.html` (the whole game), `manifest.webmanifest`, `sw.js` (offline cache), and `icons/`.

## Publish with GitHub Pages
1. Create a repo and push these files to the `main` branch (the repo root should contain `index.html` and the three folders).
2. Repo **Settings > Pages > Build and deployment**: Source = *Deploy from a branch*, Branch = `main`, folder = `/ (root)`. Save.
3. After about a minute the site is live at `https://<your-username>.github.io/<repo-name>/`. Each game is at `/<folder>/`.

PWAs need HTTPS, which GitHub Pages provides.

## Updating a game
Edit its `index.html`, then bump `CACHE_VERSION` in that game's `sw.js` (for example `v1` to `v2`). Without the bump, players can keep seeing the cached copy.

## Notes
- Saves (scores, coins, progress) live in each player's own browser storage, so they are per device.
- Paths are all relative, so the repo works under a subpath like `/<repo-name>/` and as a custom domain.
