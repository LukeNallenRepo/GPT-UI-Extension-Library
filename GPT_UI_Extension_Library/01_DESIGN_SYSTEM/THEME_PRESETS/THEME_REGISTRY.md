---
title: Theme Registry
version: 1.0.0
updated: 2026-11-23
---

# Theme Registry

All themes are domain-neutral. Any component or application may use any preset.

| Theme ID | Intended use | Visual character | Reference alignment |
|---|---|---|---|
| `data-workbench` | Operations, analytics, technical dashboards | Deep navy/teal surfaces, cyan accent, restrained status colours | Operations Command Centre, Revenue Trend, Performance Overview |
| `neutral-product` | General-purpose SaaS and project tools | Dark neutral surfaces, blue-violet accent | Neutral Product |
| `creative-studio` | Audio, visual and creator tools | Deep violet surfaces, lavender and rose accents | Creative Studio, Genesis-style project workspace |
| `warm-editorial` | Reading, documentation and content | Warm off-white surfaces, earthy accent | Warm Editorial |
| `high-contrast` | Dense interfaces and accessibility-first views | Near-black surfaces, bright text and yellow/cyan accents | High Contrast |
| `light-product` | Bright productivity applications | White and cool-grey surfaces, blue accent | Light Product |

## Theme application rules

1. Select a theme by task and information density, not by application name.
2. Keep semantic status colours distinct from brand accent colours.
3. Apply app branding as a small token override; do not fork the preset.
4. Ensure all text, charts, controls and focus indicators remain legible.
5. Support light/dark alternatives where the host can switch themes.
6. The authoritative token values remain in `theme_presets.json`.
