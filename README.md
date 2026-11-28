
# GPT UI Extension Library

**A standalone, reusable interface system for AI-assisted work.**

The GPT UI Extension Library provides domain-neutral design tokens, theme presets, component contracts, layout patterns, interaction guidance, generic application profiles and host-rendering instructions.

It helps an assistant turn interface-shaped information into clear dashboards, workspaces, analytics views, operational panels, resource libraries and other structured experiences—without rebuilding the design foundation for every application.

## Core principles

- Compose interfaces from reusable components rather than rebuilding common patterns.
- Keep shared components independent of any product, brand, data model or framework.
- Choose themes by task and content; apply product branding only as an optional host override.
- Keep data, business logic, authentication, persistence and integrations in the host application.
- Adapt to the capabilities of the rendering environment; never claim unsupported interactions.
- Prioritise accessibility, responsive layouts, legibility and data integrity.

## Six core themes

- **Data Workbench** — analytical, low-distraction.
- **Neutral Product** — general-purpose SaaS.
- **Creative Studio** — expressive creative tools.
- **Warm Editorial** — reading and documentation.
- **High Contrast** — maximum legibility.
- **Light Product** — bright productivity.

An optional **Neon Dark** preset is also included as an expressive visual treatment.

## Generic application profiles

The `12_APP_PROFILES/` directory contains reusable archetypes for general applications, data workbenches, creative studios, editorial content, operations, project workspaces, resource libraries and commerce experiences. They are not tied to any named application or external resource.

## Automatic UI enhancement

When installed in a ChatGPT Project or eligible custom GPT, the library's instructions apply consistent visual presentation to responses in that workspace. Interface-shaped requests should automatically receive a suitable UI where it materially improves comprehension or task completion. Other responses should still be clearly formatted without forcing a dashboard.

This is workspace-scoped instruction behaviour. It does not globally modify ChatGPT or other conversations, install executable software, or guarantee interactive rendering in every host.

## Standalone package

This package has no mandatory dependency.2 Host applications provide their own data, business rules, integrations, authentication and permissions.

## Install in ChatGPT

1. Extract this package.
2. Create a ChatGPT Project.
3. Upload `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` as a Project source.
4. Paste `CHATGPT_INSTRUCTIONS.md` into the Project instructions.
5. Start a chat and upload the library package or say `Mount UI extension library`.
6. Test with an interface-shaped request and an ordinary factual question.

For an eligible custom GPT, use `CHATGPT_INSTRUCTIONS.md` in Instructions and the consolidated knowledge bundle in Knowledge. See `CHATGPT_SETUP.md` for further guidance and product availability caveats.

## Repository structure

- `INSTRUCT.md` — operating, standalone, automatic-mount and UI behaviour rules.
- `MOUNT_INSTRUCT.md` — mount/reload lifecycle and status display.
- `CHATGPT_INSTRUCTIONS.md` — copy/paste workspace instructions.
- `CHATGPT_SETUP.md` — installation and verification guidance.
- `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` — consolidated knowledge source.
- `UI_EXTENSION_ARCHITECTURE.md` — architecture and package boundaries.
- `UNIVERSAL_COMPONENT_REGISTRY.md` and `02_COMPONENT_LIBRARY/` — reusable components.
- `01_DESIGN_SYSTEM/` — tokens and theme presets.
- `08_UX_ARCHITECTURE/` and `LAYOUT_REGISTRY.md` — layout patterns.
- `12_APP_PROFILES/` — generic application archetypes.
- `09_IMPLEMENTATION/` — host adapters and rendering guidance.

## Version and licence

See `VERSION`, `CHANGELOG.md` and `LICENSE.md`. The licence is retained as supplied; consult its terms before redistribution or commercial use.


## Expanded resources (2.5.0)

The library now includes a universal pattern catalogue, conversation-derived domain interface blueprints, framework/design-system ingestion specification, extended component contracts, accessibility/responsive standards, source provenance index and example compositions. See directories `13_PATTERN_LIBRARY` through `19_EXAMPLES`.

User-supplied Bootstrap, React, Tailwind, shadcn/ui, Material UI, Ant Design and custom design systems can be inventoried and mapped through the documented ingestion workflow. Their runtimes and licenses remain external and must be validated independently.
