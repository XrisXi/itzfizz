# ITZFIZZ — Scroll-Driven Hero Section Animation

A premium scroll-driven hero section built with vanilla HTML, CSS, JavaScript, and GSAP. Features a Porsche GT2 RS that sweeps in from the left and reveals the headline letter-by-letter as it passes.

---

## Live Demo & Repository

| | Link |
|---|---|
| 🌐 **Live Webpage** | `https://xrisxi.github.io/itzfizz/` |
| 📁 **GitHub Repository** | `https://github.com/XrisXi/itzfizz` |

> Replace `YOUR-USERNAME` with your actual GitHub username after deployment.

---

## Project Structure

```
itzfizz-hero/
└── index.html        ← Entire project (self-contained, car image embedded as base64)
└── README.md         ← This file
```

The project is intentionally a **single file**. The car PNG is embedded as base64 directly inside `index.html` — no external assets needed.

---

## Features

- **Scroll-driven car animation** — Porsche GT2 RS enters from the far left and drives across the screen
- **Letter reveal mechanic** — each character of "WELCOME ITZFIZZ" appears the moment the car's front bumper passes over it
- **Butter-smooth motion** — scroll events write only to JS variables; a `requestAnimationFrame` loop lerps current → target values, eliminating jank
- **GSAP intro animation** — staggered entrance with `expo.out` easing on load
- **Custom crosshair cursor** — red `+` cursor for motorsport aesthetic
- **Industrial editorial design** — Playfair Display serif + DM Mono, warm ink/paper palette

---

## Tech Stack

| Technology | Purpose |
|---|---|
| HTML / CSS / JS | Core structure and styling |
| GSAP 3.12 + ScrollTrigger | Intro animations |
| Playfair Display | Display serif font (Google Fonts) |
| DM Mono | Monospace label font (Google Fonts) |
| Barlow Condensed | UI / nav font (Google Fonts) |
| Python / Pillow | Background removal from car PNG (build step only) |

---

## How to Run Locally

1. Download `index.html`
2. Open it directly in any modern browser — no server needed
3. Scroll down to see the car animation

```bash
# Or serve with a local server (optional)
npx serve .
# then open http://localhost:3000
```

---

## Deployment — GitHub Pages (Step-by-Step)

See [`DEPLOYMENT.md`](./DEPLOYMENT.md) for the full hosting guide.

---

## Animation Architecture

### Scroll / Render Decoupling

The smoothness comes from separating concerns:

```
scroll event  →  write to target variables only  (ZERO DOM writes)
      ↓
rAF loop      →  lerp(current, target, 0.07)     (ALL DOM writes here)
```

This means even on janky scroll events, the rendered motion is always silky because the DOM is only touched once per frame.

### Car Reveal Mechanic

```javascript
// For each character:
// 1. Compute the scroll-progress value where car front passes that char
// 2. When p crosses that threshold → fade char in over 6% scroll window
// 3. Revealed chars get z-index: 20 (above car) — "left behind" effect

charThresholds[i] = (charScreenX - carFrontAtRest) / totalCarTravel;
reveal = (scrollProgress - charThresholds[i]) / 0.06;
opacity = clamp(reveal, 0, 1);
```

---

## Assignment Submission Checklist

- [x] Hero section occupies first screen (above the fold)
- [x] Letter-spaced headline: WELCOME ITZFIZZ
- [x] Impact metrics / statistics (4 stats with percentages)
- [x] On-load animation — staggered reveal with smooth easing
- [x] Statistics animate in one by one
- [x] Scroll-based animation tied to scroll progress (not time-based)
- [x] Main visual element moves smoothly based on scroll position
- [x] Easing / interpolation (smoothstep + lerp)
- [x] Performant — only `transform` properties, no layout reflows
- [x] GSAP used for intro animations
- [x] Hosted on GitHub Pages

---

## Credits

Built as a frontend animation assignment inspired by [paraschaturvedi.github.io/car-scroll-animation](https://paraschaturvedi.github.io/car-scroll-animation).
