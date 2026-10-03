# Harmonic Eccentricity — Generative Art

> A seed-based generative system for hue-harmonised ring compositions.  
> A reproducible catalogue of computational colour studies.

---

## What is this?

**Harmonic Eccentricity** is a generative design system that arranges five fundamental shapes — a line, an arc, a triangle, a rectangle, a bezier curve — around concentric rings. Each shape is placed at a precise angle, and each receives a hue offset from its ring's base. The result reads as harmony, though nothing in it is symmetrical.

Every artwork in this catalogue is defined by a single numeric seed. The same seed always produces the identical composition — making each piece **traceable, reproducible, and licensable** across textile, print, and apparel applications.

Named for the tension between *harmony* (hue relationships that hold) and *eccentricity* (shapes that never quite align), the system renders that tension visible.

---

## Live

🌐 **[View the catalogue →](https://reyrove.github.io/Harmonic-Eccentricity/)**

---

## The System

The generator combines two layers:

| Layer | Description |
|-------|-------------|
| **Concentric rings** | Five to nine circles, each carrying its own radius and rotation offset. |
| **Hue harmony** | Each shape receives a hue offset from its ring's base — a slowly rotating colour relationship. |

Both layers are driven by the same seed, ensuring deterministic output.

### Parameters

- **Layer count** — 5 to 9 concentric rings
- **Segment count** — 20 to 50 shapes per ring
- **Shape types** — 5 (line, arc, triangle, rectangle, bezier)
- **Background hue** — randomised dark HSL
- **Base hue** — randomised, drifting per shape and ring
- **Saturation / Lightness** — bounded ranges per shape

---

## Structure

```
Harmonic-Eccentricity/
├── index.html                    ← Full catalogue (single-file)
├── images/
│   ├── fav.svg
│   ├── harmonic-tote.png
│   ├── harmonic-cushion.png
│   └── ...
├── Harmonic-Eccentricity.jpg     ← Apparel mockup
└── README.md
```

The entire project is contained in a single `index.html` — no build step, no dependencies, no framework. Open it in any modern browser.

---

## Features

- **Seed-based generation** — every composition is deterministic and reproducible
- **Live catalogue** — cover, statement, plate, surfaces, process, archive, commission sections
- **Multiple surfaces** — print, scarf, textile, wallpaper — all rendered from the same seed
- **Archive of 8 seeds** — click any plate to load it into the main view
- **PNG export** — download any composition directly from the browser
- **Keyboard shortcuts** — `R` for new seed, `S` to save
- **Legal modal** — licensing, terms, and credits built in
- **Responsive** — works on desktop, tablet, and mobile
- **Mobile-first navbar** — horizontally scrollable with fade hint

---

## Usage

### Generate a new composition

Click **New Seed** or press `R`.

### Download the current composition

Click **Download** or press `S`.

### Load a seed from the archive

Click any plate in the **Archive** section.

---

## Color System

Every composition is built from HSL colour, converted to RGB at draw time:

- **Background** — a deep, desaturated hue drawn from the seed (lightness 5–20, saturation 30–70)
- **Base hue** — the starting hue for the first ring
- **Hue shift per shape** — `(baseHue + angle/2 + layer × 10) % 360`, producing a smooth sweep around the ring
- **Saturation & lightness** — bounded per shape, giving each segment its own weight

Each seed selects a unique combination — no two compositions share the same palette.

---

## Technical Notes

- Pure vanilla JavaScript — no libraries
- Canvas 2D rendering
- Custom xorshift random generator for deterministic seeds
- Device-pixel-ratio aware rendering
- Fully static rendering — one seed produces one composition, no animation loops
- Single `renderStatic()` function drives the cover, plate, framed print, all four surfaces, and all eight archive thumbnails
- `prefers-reduced-motion` respected

---

## About

**Harmonic Eccentricity** is a project by [Reyhaneh Daneshdoost](https://reyrove.github.io/) — an Iranian-born artist working at the intersection of classical textile logic and generative systems.

The work begins with a simple observation: the woven surface — repetitive, mathematically structured, infinitely variable — has always been a form of computation, long before computers.

**Harmonic Eccentricity** is an attempt to render that logic visible.

> *Colour does not repeat — it returns, shifted by every ring it passes through.*

---

## Licensing

All compositions are seed-documented and available for licensing across textile, surface, and apparel applications.

For commercial use, custom editions, or exclusive rights:

📧 **reyhanehdaneshdoost@gmail.com**

See the **Licensing** section in the live catalogue for details.

---

## Links

- 🌐 [Website](https://reyrove.github.io/)
- 📷 [Instagram](https://www.instagram.com/rey._.rove/)
- 💼 [LinkedIn](https://www.linkedin.com/in/reyhaneh-daneshdoost-730481160/)
- 🐦 [X](https://x.com/reyrove)

---

## Credits

**Design & Generative System**  
Reyhaneh Daneshdoost

**Typefaces**  
Cormorant Garamond · DM Mono

**Edition**  
Harmonic Eccentricity — Autumn 2026

---

<p align="center">
  <em>Generative Hue Harmony</em><br />
  <sub>© Reyrove Studio · All compositions reproducible by seed</sub>
</p>