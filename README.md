# Raining ThreeJS

A lightweight 3D rain simulation built with Three.js, featuring a full-screen animated particle field, atmospheric fog, and a moody night-sky style.

## Overview

This project creates a cinematic rain effect using a large number of moving particles to simulate rainfall in a 3D space. The scene includes:

- Full-screen WebGL canvas
- Dynamic raindrop motion and reset behavior
- Soft blue particle color with additive blending
- Atmospheric fog and dark background
- Responsive resizing for different screen sizes

## Tech Stack

- HTML5
- CSS3
- JavaScript (ES modules)
- Three.js

## How to Run

Because this project uses ES modules, it should be served over a local web server instead of opened directly as a file.

1. Open a terminal in the project folder.
2. Start a local server:

```bash
python3 -m http.server 8000
```

3. Visit:

```text
http://localhost:8000
```

## Project Structure

This project is intentionally simple and contained in a single page:

- `README.md` — project overview and usage instructions
- `index.html` — scene setup, particle system, animation logic, and styling

## Features

- 15,000 animated raindrops
- Wind-like horizontal drift
- Randomized respawn behavior for continuous motion
- Foggy, immersive environment for depth
- Clean fullscreen canvas presentation

## Notes

The animation is optimized for a smooth browser experience and uses a CDN-loaded Three.js module for quick setup. If you want to extend the project, the best place to start is the animation logic inside the HTML file.

## License

This project is open for personal and educational use.

## Author

Built as a creative Three.js experiment exploring particle animation and atmospheric rendering.
