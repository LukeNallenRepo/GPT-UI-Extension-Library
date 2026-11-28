---
author: "Luke Nallen"
---

# Theme Presets — AI Instructions

## Purpose
Provide reusable, app-agnostic theme foundations. These presets are not owned by any single product. Any application may adopt, combine or adapt them through semantic tokens.

## Presets
- `neutral-product`: balanced general-purpose SaaS.
- `light-product`: bright productivity and content workspace.
- `high-contrast`: legibility-first interface.
- `creative-studio`: expressive creative workspace.
- `data-workbench`: analytical and data-dense interface.
- `warm-editorial`: reading, publishing and editorial workspace.

The machine-readable token definitions are in `theme_presets.json`.

## Composition model
A theme is composed in this order:
1. Base semantic token set.
2. Light/dark or contrast mode.
3. Optional style treatment (flat, elevated, glass, outlined).
4. Application brand overrides (logo, brand accent, approved imagery and typography).
5. Component-level state tokens.

Do not bake a product name, logo, app-specific accent or domain-specific metaphor into a reusable base theme.

## AI implementation rules
- Select a preset based on content, task, environment and accessibility needs—not on the app's existing name.
- Apply semantic tokens; do not hardcode preset colours throughout component styles.
- Allow a product to switch preset without rewriting component markup.
- Keep status colours semantically stable across themes.
- Validate contrast after brand overrides.
- Provide a solid fallback for translucency and backdrop filters.
- Do not make a preset mandatory; allow custom token maps.
- Store user theme choice only through an existing, appropriate preference mechanism.

## Extension contract
Every new preset must include: id, purpose, semantic tokens, supported modes, contrast notes, component previews and validation evidence.


## Neon Dark preset

`neon-dark` is an optional reusable preset for dark interfaces using electric violet and cyan accents, layered charcoal/navy surfaces and restrained glow. It is not the default for every app. Maintain readable contrast, visible focus indicators, opaque fallbacks for translucent surfaces and reduced-motion behaviour.
