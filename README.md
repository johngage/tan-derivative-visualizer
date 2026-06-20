# Geometric Derivative of tan(θ)

An interactive geometric proof of **d/dθ tan(θ) = sec²(θ) = 1 + tan²(θ)**, following Tristan Needham's approach in *Visual Complex Analysis* (Chapter 2).

**[→ Live demo](https://johngage.github.io/tan-derivative-visualizer/)**

---

## What it does

This single-file interactive visualization animates the limit process that proves the derivative of tangent geometrically — no symbolic differentiation required. Instead:

1. **Unit circle setup** — tan(θ) is the height on the tangent line x = 1
2. **Two radial rays** — a second ray at θ + Δθ creates the increment Δtan
3. **Arc PQ ≈ Δθ** — on a unit circle, arc length equals angle in radians
4. **Similar triangles** — the tiny chord triangle at P is similar to the large secant triangle; similarity ratio = sec(θ)
5. **Limit** — as Δθ → 0, Δtan/Δθ → sec²(θ) = 1 + tan²(θ)

## Features

- **Interactive explorer** — drag sliders for θ (5°–75°) and Δθ; watch all geometry update live
- **Animate Limit** — continuously shrinks Δθ toward zero to show convergence
- **Convergence meter** — shows how close Δtan/Δθ is to sec²(θ) in real time
- **Scroll-driven narrative** — the sticky SVG panel advances through 5 geometric steps as you scroll
- **Dark/light mode** — auto-detects system preference, manual toggle available
- **Zero dependencies** — pure HTML/CSS/SVG/vanilla JS, no build step

## Usage

```bash
# Clone and open directly — no build required
git clone https://github.com/johngage/tan-derivative-visualizer.git
cd tan-derivative-visualizer
open index.html
```

Or serve with any static server:

```bash
npx serve .
# or
python -m http.server
```

## Embed

The entire visualization is a single `index.html` file with no external dependencies beyond Google Fonts. To embed in another page:

```html
<iframe
  src="https://johngage.github.io/tan-derivative-visualizer/"
  width="100%"
  height="700"
  frameborder="0"
  title="Geometric derivative of tan(θ)"
></iframe>
```

## Reference

- Needham, T. (1997). *Visual Complex Analysis*. Oxford University Press.  
  ISBN: 978-0-19-853400-2  
  The geometric proof appears in Chapter 2, §The Derivative of the Tangent Function.

- The key insight: similar triangles connecting the infinitesimal chord at P to the large secant triangle, combined with the unit-circle definition of arc length = Δθ (radians).

## Tech stack

| Layer | Choice |
|-------|--------|
| Layout | CSS Grid, sticky positioning |
| Animation | `requestAnimationFrame` + `IntersectionObserver` |
| SVG | Programmatic vanilla SVG via `createElementNS` |
| Scroll narrative | `IntersectionObserver` with animated Δθ transitions |
| Fonts | JetBrains Mono (math), General Sans (UI) |
| Color | OKLCH-based dual theme with CSS custom properties |

## License

MIT — free to use, modify, and embed in educational materials.

---

*Part of the civic technology data visualization toolkit by [John Gage](https://github.com/johngage), Berkeley CA.*
