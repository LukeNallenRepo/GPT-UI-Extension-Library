---
title: Design System
type: ui-standard
updated: 2026-11-22
author: "Luke Nallen"
---

# Design System

## Design principles
1. **Clarity before decoration:** every visual element must communicate hierarchy, state, affordance or brand.
2. **Token first:** never scatter raw colours, spacing or radii through components. Use semantic design tokens.
3. **Coherent, not uniform:** shared foundations; distinct product themes.
4. **Content-led:** test with realistic content, edge cases and data volume.
5. **Accessible by default:** contrast, keyboard, focus, reduced motion and semantic structure are baseline requirements.

## Colour architecture
Use semantic tokens rather than naming tokens after a particular screen:
- `canvas`: application background.
- `surface-1`, `surface-2`, `surface-raised`: layered panels.
- `text-primary`, `text-secondary`, `text-muted`, `text-inverse`.
- `border-subtle`, `border-strong`, `focus-ring`.
- `accent-primary`, `accent-secondary`, `accent-soft`.
- `success`, `warning`, `danger`, `info` and their soft backgrounds.

Create light and dark values for every semantic token. Do not rely on colour alone to communicate status; pair it with text, iconography or shape. Keep brand accents for actions and meaningful emphasis rather than colouring every panel.

## Typography
- Use a highly legible UI sans-serif for interface text; reserve display faces for short titles.
- Establish a compact type scale (e.g. 12/14/16/18/24/32/40px) and document line heights and weights.
- Body text should normally be 14–16px or larger; dense data labels may be smaller only when still readable.
- Use tabular numerals for metrics, prices, IDs and timestamps.
- Limit each screen to a small number of weights and sizes. Avoid all-caps for long labels.

## Spacing, geometry and layout
- Use a consistent 4px or 8px base spacing scale.
- Define radii by role: small controls, standard cards, large feature surfaces and pills.
- Use a responsive grid with consistent gutters and max-widths.
- Apply a spacing rhythm: group related controls tightly; separate unrelated sections more clearly.
- Prefer alignment and whitespace over unnecessary borders.
- Use bento layouts only when modules have meaningful differences in importance or content; avoid arbitrary tile mosaics.

## Elevation, borders and effects
- Establish 3–4 elevation levels. Shadows should indicate layering, not decorate every card.
- Glass surfaces are optional accents: maintain opaque fallbacks, readable contrast and restrained blur.
- Gradients and glow should guide attention to active or featured elements, not obscure text.
- Use subtle borders to define boundaries where surface contrast is insufficient.

## Theme system
- Generic presets live in `THEME_PRESETS/theme_presets.json`; they are not owned by any specific app.
- Select a preset by usability context (general product, light workspace, high contrast, creative studio, data workbench or editorial), not by product name.
- Compose base preset → mode → optional style treatment → app brand overrides.
- Keep app logos, brand accents and approved imagery in the app layer.
- Support system preference plus an explicit user override where appropriate.
- Persist theme preference only through an existing, suitable settings mechanism.
- Ensure charts, diagrams, focus rings, overlays and embedded editors respond to theme changes.
- See `THEME_PRESETS/INSTRUCT.md` for AI selection and extension rules.

## Acceptance checklist
- [ ] Semantic tokens exist for both light and dark themes.
- [ ] Contrast is checked for text, controls, charts and focus indicators.
- [ ] Spacing, radii and typography use documented scales.
- [ ] Brand assets retain their approved geometry and proportions.
- [ ] Theme switching does not break charts, dialogs or third-party surfaces.

