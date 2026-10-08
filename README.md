# KNACKSAT-3 Explorer

Interactive web page for the KNACKSAT-3 1U CubeSat: a 3D model with per-part specifications, and an orbit & ground-station simulation. Languages: Thai, English, Chinese, German.

It is a static site with no build step. Everything runs in the browser.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole page (styles, scripts and images are inside this file) |
| `vendor/three.min.js`, `vendor/OrbitControls.js` | three.js r147 for 3D rendering (MIT license, `vendor/three-LICENSE.txt`) |
| `render.yaml` | Render Blueprint for a static site |

## Run locally

Open `index.html` in a browser, or serve the folder:

```
python3 -m http.server 8000
```

Then open http://localhost:8000

## Deploy on Render

1. Push this folder to a GitHub (or GitLab) repository, with `index.html` at the repository root.
2. In Render, choose **New → Static Site** and connect the repository.
3. Settings:
   - Build Command: leave empty
   - Publish Directory: `.`
4. Click **Create Static Site**. Render gives you a `*.onrender.com` URL.

Alternatively, choose **New → Blueprint** and select the repository; Render reads `render.yaml` and creates the static site for you.

## Notes

- Fonts load from Google Fonts. Without internet the page falls back to system fonts.
- The orbit simulation assumes an ISS-like orbit (400 km, 51.6°); see the Notes section on the page.
