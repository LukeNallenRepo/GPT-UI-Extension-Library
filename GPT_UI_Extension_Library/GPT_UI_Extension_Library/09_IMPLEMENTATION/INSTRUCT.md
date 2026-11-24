---
title: Implementation
type: ui-standard
updated: 2026-11-22
---

# Implementation

## Architecture
Keep design tokens, primitives, product components, domain logic and data services in separate layers. Prefer typed component APIs and predictable state ownership. Avoid building a generic framework before a real reuse case exists.

## React and TypeScript
- Use semantic components and typed props.
- Keep components small and composable.
- Use stable keys and predictable state transitions.
- Handle loading, error, empty and stale data states explicitly.
- Avoid unnecessary global state; local state belongs near its owner.
- Add tests for critical interactions and domain-to-UI mapping.

## CSS and Tailwind
Use CSS variables for semantic theme tokens. Tailwind utilities may express layout and spacing, but shared design values should remain centralised. Avoid arbitrary one-off values unless documented as a deliberate exception. Scope styles to prevent leakage between embedded applications.

## Libraries
Use the libraries already present in the target app where practical. Do not add a dependency merely because the library recommends it. Verify maintenance, bundle cost, accessibility, licensing and compatibility before adoption.

## Integration workflow
1. Inspect current app structure and existing design language.
2. Identify shared components and dependencies.
3. Map screens and key user journeys.
4. Define tokens and component contracts.
5. Implement incrementally without replacing working business logic.
6. Test responsive layouts, keyboard operation and all UI states.
7. Run existing lint, typecheck, tests and production build.
8. Record changed files, validation results and known limitations.

## Code quality
Avoid duplicate components, oversized files, hidden side effects, fake data in production screens and silent error swallowing. Keep secrets out of client bundles. Do not claim build success without executing and inspecting the build result.



## ChatGPT rendering adapter

Use `CHATGPT_VISUAL_ADAPTER.md` when the target surface is ChatGPT. Prefer native visual/interactive composition, then a structured static visual, then Markdown fallback. The archive is portable documentation and does not itself install executable runtime code.
