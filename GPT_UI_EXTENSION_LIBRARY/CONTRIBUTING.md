---
author: "Luke Nallen"
---

# Contributing

Thank you for helping improve the GPT UI Extension Library.

## Scope

Contributions should improve reusable, portable UI specifications, components, layouts, themes, interaction patterns, adapters or documentation. Keep application-specific business logic and private data outside the shared library.

## Before proposing a change

1. Check `UNIVERSAL_COMPONENT_REGISTRY.md` and `02_COMPONENT_LIBRARY/component_registry.json` for an existing equivalent.
2. Prefer extending an existing component contract over creating a near-duplicate.
3. Identify the intended component family and logical import package in `UI_EXTENSION_ARCHITECTURE.md`.
4. Confirm that the change does not introduce private information, credentials, personal records, proprietary assets without permission or unnecessary dependencies.

## Component submission requirements

A new or materially changed component should document:

- Stable component ID, name, family and version.
- Purpose and composition role.
- Required and optional props, with data shapes.
- Events/callbacks and state ownership.
- Loading, empty, error, disabled and success states where applicable.
- Theme tokens consumed.
- Responsive behaviour and accessibility requirements.
- Dependencies and host-adapter requirements.
- At least one representative composition.
- Evidence status: `SOURCE-VERIFIED`, `IMPLEMENTATION-VERIFIED`, `DOCUMENTED`, `INFERRED`, `PROPOSED` or `NOT INSPECTED`.

## Registry maintenance

When adding a reusable component:

1. Update `02_COMPONENT_LIBRARY/component_registry.json`.
2. Update `UNIVERSAL_COMPONENT_REGISTRY.md`.
3. Update the relevant family instruction file or template.
4. Update `CHANGELOG.md`.
5. Validate JSON and internal Markdown links.
6. Preserve stable IDs and existing component definitions unless a migration is documented.

Do not label a component implementation-verified based solely on a written specification or screenshot.

## Themes and visual design

- Prefer design tokens over hard-coded values.
- Keep semantic status colours distinct from brand accents.
- Check text contrast, focus visibility and non-colour status cues.
- Respect reduced-motion preferences.
- Keep project-specific brand overrides separate from generic presets.

## Pull request checklist

- [ ] The change is reusable and not unnecessarily app-specific.
- [ ] No secrets, credentials, personal records or private source files are included.
- [ ] Component and theme registries are updated where needed.
- [ ] JSON files parse successfully.
- [ ] Internal links and referenced paths are valid.
- [ ] Evidence labels accurately describe implementation status.
- [ ] Documentation and changelog are updated.
