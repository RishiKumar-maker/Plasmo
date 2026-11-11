# The Hollow House
Low-poly first-person ghost-hunting game (Willow Street layout). Pure static site: no build step, no CDN.

## Deploy on GitHub Pages (2 options)
**A. Simplest:** push this whole folder to a repo → Settings → Pages → *Deploy from a branch* → `main` / `(root)`.
**B. Actions:** Settings → Pages → Source: *GitHub Actions*. The included `.github/workflows/pages.yml` deploys on every push to `main`.
Then open `https://<user>.github.io/<repo>/`.

## Structure
- `index.html` – the game
- `assets/ghost.glb`, `assets/props.glb` – 3D models (fall back to simple shapes if missing)
- `lib/` – three.js r160 + loaders, vendored so the game never depends on a CDN
- `sw.js` – service worker: always fresh online, works offline after the first visit
- `.nojekyll` – tells Pages to serve files as-is

GitHub Pages gzips text/JS automatically. Models only load over http(s) (not by double-clicking the file); to test locally run `python3 -m http.server` in this folder.

## Graphics quality (menu buttons, remembered)
- **Low** – Chromebook mode: flat lighting, no shadows, auto resolution scaling.
- **Medium** – + filmic tone mapping and film grain.
- **High** – + PBR materials with procedural normal maps, real-time flashlight shadows, antialiasing.

## Controls
WASD move · Shift sprint · Mouse look · E interact/use · 1–5 tools · F flashlight · J journal
