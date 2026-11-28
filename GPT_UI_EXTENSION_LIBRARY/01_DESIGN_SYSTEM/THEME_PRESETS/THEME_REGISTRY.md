---
author: "Luke Nallen"
---

# Theme Registry

The six core presets below are the reusable themes shown in the library's visual reference. Every preset is domain-neutral and can be used by any application.

| Theme ID | Display name | Intended use | Visual character |
|---|---|---|---|
| `data-workbench` | Data Workbench | Analytics and data-dense work | Deep navy/teal surfaces, cyan accent, restrained status colours |
| `neutral-product` | Neutral Product | General-purpose SaaS | Dark neutral surfaces, blue-violet accent |
| `creative-studio` | Creative Studio | Expressive creative tools | Deep violet surfaces, lavender and rose accents |
| `warm-editorial` | Warm Editorial | Reading and documentation | Warm off-white surfaces, earthy accent |
| `high-contrast` | High Contrast | Maximum legibility | Near-black surfaces, bright text and yellow/cyan accents |
| `light-product` | Light Product | Bright productivity | White and cool-grey surfaces, blue accent |

## Additional optional preset

`neon-dark` is retained as an optional expressive treatment for applications that benefit from violet/cyan lighting accents. It is not a replacement for any of the six core presets.

## Theme application rules

1. Select a theme by task, content and accessibility needs, not application name.
2. Keep semantic status colours distinct from brand accent colours.
3. Apply app branding as a small host-supplied token override; do not fork a preset.
4. Ensure text, charts, controls and focus indicators remain legible.
5. Support light/dark alternatives where the host can switch themes.
6. The authoritative token values remain in `theme_presets.json`.
