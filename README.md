# NEXUS — Augmented Human Technology Landing Page

A fully responsive, single-file cyborg-themed landing page built with pure HTML, CSS, and vanilla JavaScript. No frameworks. No dependencies. Just one file that opens in any browser.

---

## Preview

```
NEXUS — Generation 7 Augmentation System
Transcend Human Limits // Nexus Augmentation Corp — 2047 //
```

Dark, high-contrast sci-fi aesthetic with animated SVG cyborg illustration, glitch effects, scroll-triggered animations, and a custom cursor — all self-contained in `cyborg-landing.html`.

---

## Features

### Visual Design
- **Custom SVG cyborg figure** — hand-crafted illustration with spinning mechanical eye, rotating orbit rings, floating HUD overlays, and idle float animation
- **Cyberpunk color palette** — deep space black `#030810` with electric cyan `#00f5ff` and warning red `#ff2d4e`
- **CRT scanline overlay** — subtle repeating gradient simulating a cathode-ray monitor
- **Perspective grid background** — fixed CSS grid with radial glow at the top
- **Glitch text effect** — hero headline flickers with offset cyan/red ghost layers

### UI Components
- **Custom cursor** — lagging ring tracker with center dot; morphs on hover over interactive elements
- **Animated stat counters** — hero numbers count up from zero on page load using eased JavaScript
- **Scrolling marquee** — infinite tech-label ticker between the hero and features sections
- **Spec bars** — IntersectionObserver-triggered animated progress bars in the Tech Specs section
- **Scroll reveal** — staggered fade-in and slide-up entrance for every card and section heading
- **Parallax hero** — cyborg figure shifts subtly on scroll for depth
- **Nav active state** — current section link highlights as you scroll

### Page Sections

| Section | Description |
|---|---|
| **Navigation** | Fixed, blurred backdrop nav with logo, links, and CTA button |
| **Hero** | Full-viewport intro with headline, description, CTAs, live stats, and cyborg SVG |
| **Marquee** | Scrolling ticker of augmentation technology labels |
| **Core Augmentations** | 6-card feature grid with inline SVG icons and hover top-border reveal |
| **Tech Specs** | Two-column layout with animated progress bars and bullet list |
| **Augmentation Series** | 3-tier product/pricing cards (NEXUS-1, NEXUS-4, NEXUS-7) with featured highlight |
| **Field Reports** | Testimonial cards with star-style rating indicators |
| **CTA** | Pulsing concentric ring animation with consultation call-to-action |
| **Footer** | 4-column footer with brand info, links, social buttons, and system status |

---

## Getting Started

No build step. No package manager. Just open the file.

```bash
# Clone or download, then:
open cyborg-landing.html

# Or serve locally for best results:
npx serve .
# then visit http://localhost:3000/cyborg-landing.html
```

---

## File Structure

```
cyborg-landing.html   # The entire project — HTML + CSS + JS in one file
README.md             # This file
```

Everything lives in a single HTML file:

```
cyborg-landing.html
├── <head>
│   ├── Google Fonts (Orbitron, Rajdhani, Share Tech Mono)
│   └── <style> — all CSS custom properties, layout, animations
├── <body>
│   ├── Custom cursor elements
│   ├── Grid background + scanlines (fixed overlays)
│   ├── <nav>
│   ├── <section class="hero">
│   ├── <div class="marquee-wrap">
│   ├── <section id="augmentation">
│   ├── <section id="specs">
│   ├── <section id="models">
│   ├── <section id="testimonials">
│   ├── <section class="cta-section">
│   ├── <footer>
│   └── <script> — cursor, counters, IntersectionObservers, parallax
```

---

## Typography

| Font | Usage | Weight |
|---|---|---|
| **Orbitron** | Headings, logo, buttons, labels | 400 – 900 |
| **Rajdhani** | Body text, descriptions | 300 – 700 |
| **Share Tech Mono** | Tags, codes, section labels, stats | 400 |

Loaded via Google Fonts CDN. No self-hosting required.

---

## CSS Architecture

All theming is driven by CSS custom properties on `:root`:

```css
:root {
  --cyan: #00f5ff;          /* Primary accent */
  --cyan-dim: #00bcd4;      /* Muted accent */
  --cyan-dark: #006a75;     /* Dark accent for gradients */
  --red: #ff2d4e;           /* Warning / secondary accent */
  --bg: #030810;            /* Page background */
  --bg2: #060d1a;           /* Alternate section background */
  --surface: #0d1f36;       /* Card surface */
  --text: #e0f4ff;          /* Primary text */
  --text-dim: #7ba8be;      /* Secondary text */
  --glow: 0 0 20px rgba(0,245,255,0.25), 0 0 60px rgba(0,245,255,0.1);
}
```

To retheme, change the values in `:root` — the entire page updates.

---

## JavaScript

Three vanilla JS systems, no libraries:

**Cursor tracker** — uses `requestAnimationFrame` with lerp (linear interpolation) for the trailing ring effect. The dot follows instantly; the ring lags at 15% per frame.

**IntersectionObserver** — three separate observers handle scroll reveals (fade + slide), stat counter animations (count up from 0 with cubic ease-out), and spec bar width transitions.

**Parallax + nav highlight** — a single `scroll` event listener drives the hero SVG parallax offset and updates the active nav link based on current section position.

---

## Responsive Breakpoints

| Breakpoint | Layout changes |
|---|---|
| `> 1024px` | Full layout — 3-column grids, side-by-side specs, hero SVG visible |
| `≤ 1024px` | 2-column grids, stacked specs, hero SVG reduced opacity |
| `≤ 768px` | Single column, nav links hidden, hero SVG hidden, stats wrap |

---

## Customisation Guide

**Change the brand name** — search for `NEXUS` and replace throughout the HTML and the logo `nav-logo` span.

**Add a section** — copy any existing `<section>` block, give it a new `id`, and add the matching anchor to `.nav-links`.

**Update pricing / features** — edit the `.model-card` blocks in the Models section. The featured card is marked with class `featured`.

**Change fonts** — update the Google Fonts `<link>` URL and the `font-family` values in the CSS variables / utility classes.

**Adjust animation speed** — `marquee-track` animation duration is `30s`; spec bars transition is `1.5s`; cursor lerp factor is `0.15` in the JS.

---

## Browser Support

Works in all modern browsers. The custom cursor is hidden on touch devices (touch events don't trigger `mousemove`). Scroll reveal and counters degrade gracefully if JavaScript is disabled — content is still fully visible.

| Browser | Support |
|---|---|
| Chrome 90+ | ✓ Full |
| Firefox 88+ | ✓ Full |
| Safari 14+ | ✓ Full |
| Edge 90+ | ✓ Full |
| Mobile browsers | ✓ Responsive (cursor disabled) |

---

## License

This project is released for personal and commercial use. Attribution appreciated but not required.

---

*// NEXUS Augmentation Corp — 2047 // All Systems Nominal //*
