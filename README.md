# JNTU 3D Model Viewer

> **A minimal Three.js scene that loads and orbits a 3D GLTF model in the browser — no build step required.**

## Overview

This is a small, self-contained [Three.js](https://threejs.org/) demo that renders a 3D model in the browser and lets you orbit, pan, and zoom around it. It is a hands-on learning project for loading GLTF assets and wiring up interactive camera controls. Three.js and its loaders are pulled straight from a CDN as ES modules, so there is nothing to install or bundle — just serve the folder and open it.

## Features

- Renders a 3D GLTF model (`dino` by default) using the Three.js `GLTFLoader`.
- Interactive camera via `OrbitControls` — drag to rotate, scroll to zoom (with a boosted zoom speed).
- Transparent (alpha) WebGL renderer over a dark page background.
- Directional and ambient lighting so the model is clearly visible.
- Responsive canvas that resizes with the browser window.
- Ships with several swappable models: `dino`, `dino2`, and `eye`.

## Tech Stack

- **Three.js** `0.129.0` (loaded from the Skypack CDN as an ES module)
- `OrbitControls` and `GLTFLoader` from the Three.js examples
- Plain **HTML**, **CSS**, and vanilla **JavaScript** (ES modules) — no framework, no bundler

## Getting Started

Because the app uses ES module imports and fetches local model files, it must be served over HTTP (opening `index.html` directly via `file://` will not work). Any static file server will do:

```bash
# Clone the repo
git clone https://github.com/nickthelegend/three.git
cd three

# Serve the folder with any static server, e.g.:
python3 -m http.server 8000
# or
npx serve .
```

Then open <http://localhost:8000> in your browser.

To display a different model, change the `objToRender` value in `js/main.js` to one of the folders under `models/` (e.g. `dino2` or `eye`).

## Project Structure

```
three/
├── index.html        # Page markup and #container3D mount point
├── css/
│   └── style.css     # Full-viewport canvas and page styling
├── js/
│   └── main.js       # Scene, camera, lights, OrbitControls, GLTF loading
└── models/           # GLTF/FBX assets and textures
    ├── dino/         # Default model
    ├── dino2/
    └── eye/
```

## Credits

3D models are used under Creative Commons Attribution:
- "Eye Free Model 3D" by Oscar Creativo
- "Juvenile Teratophoneus curriei" by rankinstudio

---

Built by [nickthelegend](https://github.com/nickthelegend) · [nickthelegend.tech](https://nickthelegend.tech)
