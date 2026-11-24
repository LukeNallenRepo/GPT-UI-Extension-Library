---
title: Universal App Builder Instructions
version: 1.0.0
updated: 2026-11-23
status: reusable-build-workflow
---

# Universal App Builder Instructions

## Mission

Build new applications by composing the shared UI extension library. The app's domain, data model and brand may vary; the component system remains reusable.

## Build sequence

1. **Define the application surface:** identify the user, primary task, information hierarchy, key actions and data sources.
2. **Choose a layout:** select an application shell, dashboard, project workspace, analytics view, creative editor or document view from `LAYOUT_REGISTRY.md`.
3. **Choose a theme:** select one preset from `01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`. Add only the minimum brand override necessary.
4. **Compose components:** use registered components. Prefer composition over app-specific forks.
5. **Define data contracts:** map each displayed field to a source field. Clearly label demo/sample data.
6. **Define interactions:** state which controls are navigational, local-state, data-mutating or external actions. Never render a control that appears functional but has no action.
7. **Define responsive behaviour:** specify mobile, tablet and desktop layouts.
8. **Render:** use the best available adapter. In ChatGPT, follow `09_IMPLEMENTATION/CHATGPT_VISUAL_ADAPTER.md`.
9. **Validate:** run the quality checklist in `11_QUALITY_CONTROL/INSTRUCT.md`.
10. **Register:** add genuinely reusable new components to both component registries; add app-specific composition to `03_APP_LIBRARY/APP_INVENTORY.*` only when appropriate.

## Composition rules

- A component may contain other components, but its contract must declare those dependencies.
- A layout controls page-level structure; a component controls a reusable functional or visual unit.
- Theme tokens control appearance; component props control content and behaviour.
- App profiles may select components and override brand tokens but must not redefine shared components.
- Charts must use real source values or carry a prominent illustrative-data disclosure.
- Empty, loading, error and stale states are first-class interface states.
- Avoid decorative UI that competes with the user's task.
- Preserve the user's existing visual references when explicitly asked to extend an existing app.

## Output expectation

For a UI-building request, produce the actual visual interface when the host supports it. Do not answer only with a list of components or a Markdown description unless the user asks for a specification. When a visual runtime is unavailable, provide a structured preview/specification and clearly state what remains to be implemented.
