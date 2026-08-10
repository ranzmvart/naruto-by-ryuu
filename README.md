# NARUTO × SASUKE — Hand-Powered Ninja Experience

Realtime hand tracking webapp: open your hand and unleash **Rasengan (Naruto)** and **Chidori (Sasuke)** — right in your browser, no installs, no cloud.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![MediaPipe](https://img.shields.io/badge/MediaPipe-Hand%20Tracking-00C8FF?style=flat-square)
![Netlify](https://img.shields.io/badge/Deployed%20on-Netlify-00C7B7?style=flat-square&logo=netlify&logoColor=white)

---

## Demo

| Landing page | Experience |
| :---: | :---: |
| Apple-style bento grid homepage with cinematic Rasengan vs Chidori intro | Live camera + hand tracking with Rasengan/Chidori effects & sound |

Site is deployed and auto-rebuilt on every push from the `main` branch.

## Features

- **Real-time hand tracking** — 21 landmarks per hand via MediaPipe, rendered as a bright blue neon skeleton
- **Rasengan power** — open your left hand and a blazing spiral follows your palm
- **Chidori power** — open your right hand and crackling blue lightning fans out at your fingertips
- **Both hands at once** — Naruto and Sasuke can clash simultaneously
- **3D effect videos** — screen-blended transparent effects (`assets/naruto.mp4`, `assets/sasuke.mp4`)
- **Sound effects** — Rasengan & Chidori SFX trigger on hand open, with on/off toggle
- **Camera switching** — front/back camera button for devices with multiple cameras
- **Cinematic landing** — webinar-style intro (Rasengan vs Chidori crash), bento grid layout, glassmorphism, fully responsive
- **BGM player** — "Shouting Star" by HOME MADE 家族 with animated equalizer
- **Loading intro** — Rasengan and Chidori collide at the center of the screen while MediaPipe boots up
- **Private by design** — hand tracking runs 100% on-device; the camera feed never leaves the browser

## How to use

1. Open the site and click **Enter the Arena** (or `experience.html`).
2. Allow the camera when prompted — nothing is recorded or uploaded.
3. **Left hand open** → Rasengan · **Right hand open** → Chidori.
4. Move your palm to steer the power; close your hand to bank it.

> On mobile, use the **camera button** (bottom right) to switch between front/back camera.

## Tech stack

- Vanilla HTML / CSS / JavaScript — zero dependencies, no build step
- [MediaPipe Hands](https://developers.google.com/mediapipe/solutions/vision/hand_landmarker) (browser CDN) for hand tracking
- Static hosting on [Netlify](https://www.netlify.com) via `netlify.toml`

## Project structure

```
├── index.html          # Landing page (bento grid + cinematic intro)
├── experience.html     # Hand-tracking experience app
├── netlify.toml         # Netlify build config (static publish + COEP/COOP headers)
├── assets/
│   ├── naruto.mp4       # Rasengan effect video
│   ├── sasuke.mp4       # Chidori effect video
│   ├── amv.mp4          # Naruto vs Sasuke AMV (landing hero)
│   └── sound/
│       ├── rasengan.mp3 # Rasengan SFX
│       ├── chidori.mp3  # Chidori SFX
│       └── shouting-star.mp3 # BGM (landing page)
```

## Run locally

Just open the file — no server needed:

```bash
# option 1: double-click index.html
# option 2: serve the folder
python -m http.server 8000
# or: npx serve .
```

> Note: camera APIs generally require `https` or `localhost` — use the local server for best results.

## Deploy to Netlify

The repo is pre-configured with `netlify.toml` (publish dir: `.`, plus COEP/COOP headers for MediaPipe's WASM). To connect:

1. Push this repo to GitHub.
2. In Netlify: **Add new site → Import an existing project** → pick the repo.
3. Build command: *(empty)*, publish directory: `.`
4. Deploy. Every `git push` triggers an automatic redeploy.

## Disclaimer

Fan-made project. Not affiliated with, endorsed by, or associated with the Naruto franchise, Shueisha, or Studio Pierrot. All character names, effects, and trademarks belong to their respective owners. BGM & SFX used for personal/educational purposes.