# PixelTone — Image Color Analyzer

A pixel-level image color analysis tool that maps every pixel of any image to one of 11 human-readable color categories and generates a percentage breakdown chart.

## 🔴 Live Demo
👉 [Try it here](https://YOUR-USERNAME.github.io/pixeltone-color-analyzer)

No installation. No backend. Open in browser and use.

---

## What It Does
- Analyzes every pixel — no sampling
- Maps each pixel to one of 11 categories: White, Black, Red, Green, Yellow, Blue, Brown, Purple, Pink, Orange, Gray
- Outputs a horizontal bar chart sorted by percentage
- Results in under 3 seconds

---

## How to Use
1. Click the Live Demo link above
2. Drag and drop any image (JPEG, PNG, WebP, BMP)
3. Click Analyze
4. See the color breakdown instantly

---

## The Algorithm
Converts RGB → HSV, then classifies through 4 gates in strict priority order:

| Priority | Gate | Logic |
|----------|------|-------|
| 1 | Achromatic | S < 6% → Black / White / Gray by brightness |
| 2 | Dark Gate | V < 12% → Black regardless of hue |
| 3 | Pastel Detection | S 4–15%, V > 72% → routed to correct hue |
| 4 | Brown Trap | Hue 0°–50°, S < 65%, V < 72% → Brown |
| 5+ | Hue Ranges | Red, Orange, Yellow, Green, Blue, Purple, Pink |

---

## Input Validation
- ✅ Accepted formats: JPEG, PNG, WebP, BMP
- ❌ Rejected: GIF, HEIC, TIFF, SVG
- Minimum resolution: 100 × 100 px
- Maximum file size: 25 MB
- PNG transparency: fully transparent pixels excluded from count

---

## Sample Output

| Color | Example % |
|-------|-----------|
| Brown | 49.1% |
| Black | 21.3% |
| Green | 16.5% |
| Yellow | 4.7% |
| Orange | 3.9% |

---

## Built With
- Vanilla HTML / CSS / JavaScript
- Browser Canvas API for pixel-level access
- Zero external dependencies — single file, works offline
- Prototype directed and built using Claude (Anthropic) as LLM
- No backend, no server, no installation required

---

## PRD
Full 9-section Product Requirements Document available on request.

Covers: exact use case, input specifications, color mapping algorithm with hue thresholds, output specification, competitive analysis, success metrics, risks, assumptions, and V2 roadmap.

---

## V2 Roadmap
- HEIC format support (iPhone default format)
- Grid-based spatial color analysis
- Export chart as PNG / CSV
- HSL and OKLCH color code output
- Side-by-side image comparison

---

*Built by Harshita as part of a Product Management assignment.*
