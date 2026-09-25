# Gesture Controlled 3D Particles

A browser-based 3D particle system you control with your bare hands — no mouse, no keyboard. Point your webcam at yourself, and use hand gestures to move, pinch, and morph a swarm of 12,000 glowing particles between shapes like a sphere, heart, flower, Saturn, and a fireworks burst.

Built with **Three.js** for rendering and **MediaPipe Hand Landmarker** for real-time hand tracking, all in a single self-contained HTML file.

## ✨ Features

- **Real-time hand tracking** via your webcam, powered by MediaPipe's GPU-accelerated hand landmark model
- **12,000 animated particles** rendered with additive blending for a soft, glowing look
- **Five morphable shapes** — Sphere, Heart, Flower, Saturn, Fireworks — with smooth lerp-based transitions
- **Gesture controls**:
  - 🖐 **Move your hand** — drag and tilt the particle system
  - 👌 **Pinch** (thumb + index finger together) — collapse and pull particles toward your hand
  - ✋ **Open hand** — scatter and swirl particles outward
  - 👉 **Move to the right edge of the screen** — cycle to the next shape
- **Idle animation** — subtle noise-based motion keeps the particles alive even without hand input
- Zero build tools, zero dependencies to install — just open the file in a browser

## 🚀 Getting Started

Because this project accesses your webcam, most browsers require it to be served over `http://localhost` or `https://` rather than opened directly as a `file://` URL.

1. Clone the repo:
   ```bash
   git clone https://github.com/<your-username>/<your-repo>.git
   cd <your-repo>
   ```
2. Serve the folder locally, for example with Python:
   ```bash
   python3 -m http.server 8000
   ```
3. Open `http://localhost:8000` in your browser.
4. Allow camera access when prompted, and hold your hand up in front of the webcam.

## 🎮 Controls

| Gesture | Effect |
|---|---|
| Move hand | Moves and tilts the particle formation |
| Pinch (thumb + index close together) | Collapses particles inward, pulling them toward your fingertip |
| Open hand | Expands and swirls particles outward |
| Hand near the right edge of the frame | Cycles to the next shape |

## 🛠 Tech Stack

- [Three.js](https://threejs.org/) (r160) — WebGL rendering and particle system
- [MediaPipe Tasks Vision](https://developers.google.com/mediapipe/solutions/vision/hand_landmarker) — hand landmark detection
- Vanilla JavaScript (ES modules), HTML, and CSS — no framework, no bundler

## 📋 Requirements

- A modern browser with WebGL and WebGPU/GPU delegate support (recent Chrome or Edge recommended)
- A webcam
- An internet connection on first load (Three.js, MediaPipe, and the hand-tracking model are loaded from CDNs)

## 📁 Project Structure

```
.
└── index.html   # Entire app: markup, styling, and logic in one file
```

## 🎨 Customization

A few easy tweaks to experiment with, all near the top of the `<script>` block in `index.html`:

- `PARTICLE_COUNT` — number of particles (default `12000`)
- `PARTICLE_SIZE` — size of each particle point
- `LERP_SPEED` — how quickly particles morph into a new shape
- `SHAPES` — the array and order of shapes to cycle through

## ⚠️ Known Limitations

- Only tracks a single hand at a time
- Tracking accuracy depends on lighting and webcam quality
- Requires GPU delegate support for smooth hand-tracking performance

