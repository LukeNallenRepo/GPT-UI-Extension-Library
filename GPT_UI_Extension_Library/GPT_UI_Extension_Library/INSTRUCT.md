---
title: GPT UI Extension Library
version: 2.3.0
updated: 2026-11-23
status: portable-composable-ui-standard
---

# GPT UI Extension Library

## Mission

A domain-neutral library of reusable visual design systems, components, layouts, interaction patterns, application compositions and host adapters. It is intended to be imported into another ChatGPT account or used by an AI assistant, developer or application runtime to build new interfaces.

The library is a component system, not a set of fixed screenshots. Components must remain independent of any one app, brand, project or data model. Apps are compositions of shared components plus a small app-specific configuration layer.

## Start here

1. Read this file.
2. Read `MOUNT_INSTRUCT.md` to import the library into a new ChatGPT account or assistant workspace.
3. Read `UI_EXTENSION_ARCHITECTURE.md` for the three-layer architecture, logical import packages, expanded catalogue and optional Neon Dark visual treatment.
4. Read `UNIVERSAL_COMPONENT_REGISTRY.md` and `02_COMPONENT_LIBRARY/component_registry.json` to discover available components.
5. Read `01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json` to select a visual theme.
6. Read `08_UX_ARCHITECTURE/INSTRUCT.md` and `LAYOUT_REGISTRY.md` to select a layout.
7. Read `APP_BUILDER_INSTRUCT.md` to compose a new app.
8. Read `09_IMPLEMENTATION/CHATGPT_VISUAL_ADAPTER.md` when rendering inside ChatGPT.
9. Read `09_IMPLEMENTATION/markdown_dashboard_renderer.md` when rendering Markdown documents as dashboards.

## Core principles

- **Visual-first:** if the host can render a visual, structured or interactive representation, use it instead of returning a plain Markdown summary. Use a static visual when interaction is unavailable.
- **Composable:** build interfaces from independently reusable components. Do not duplicate a component to create an app-specific variant when props, theme tokens or composition can solve it.
- **Portable:** keep component definitions framework-independent. Provide host adapters rather than coupling the library to one runtime.
- **Progressive fidelity:** prefer native interactive rendering; otherwise use a static visual; otherwise use a structured Markdown fallback that preserves hierarchy and meaning.
- **Data integrity:** never invent metrics, activity, status, timestamps, chart points, user counts or completion values. Mark sample data as illustrative.
- **Separate concerns:** data and business logic belong to the host app; presentation components receive typed inputs and emit documented events.
- **Accessible by default:** semantic structure, keyboard support, focus visibility, contrast, reduced motion and non-colour status cues.
- **Responsive by default:** design for narrow mobile widths first, then expand to tablet and desktop.
- **Evidence labels:** distinguish `SOURCE-VERIFIED`, `IMPLEMENTATION-VERIFIED`, `DOCUMENTED`, `INFERRED`, `PROPOSED` and `NOT INSPECTED`.
- **Preserve provenance:** retain source file paths, component IDs, versions and app-profile references when reusing existing material.

## Component contract

Every component definition must specify:

- Stable ID, name, family and version.
- Purpose and composition role.
- Required and optional props, including data shape.
- Events/callbacks and state ownership.
- Loading, empty, error, disabled and success states where relevant.
- Theme tokens consumed.
- Responsive behaviour and accessibility requirements.
- Dependencies and host adapter requirements.
- At least one example composition.
- Evidence/status label.

## Rendering decision

For each requested UI:

1. Identify the information hierarchy and user task.
2. Select a layout from `LAYOUT_REGISTRY.md`.
3. Select a theme preset; apply brand overrides only where supplied.
4. Compose components from the registry.
5. Bind all values to actual source data or explicitly labelled illustrative data.
6. Render through the best available host adapter.
7. If the host lacks a required capability, degrade gracefully without pretending the missing capability exists.

## Versioning and maintenance

- Library version uses semantic versioning.
- Component IDs remain stable; breaking prop/event changes require a major component version.
- Additive components and optional props are minor changes.
- Corrections to descriptions and examples are patch changes.
- Update the JSON registry and human-readable registry together.
- Do not remove legacy app profiles or source material without a documented migration.

## Default UI enhancement behaviour

**Automatic UI enhancement is enabled by default whenever this library is mounted.**
Do not wait for the user to say “make it a dashboard” when the requested content
clearly benefits from an interface. Apply the following decision rule on every turn:

1. If the user requests, provides, or is working with a dashboard, status view,
   operational workflow, project overview, comparison, data report, file inventory,
   task queue, agent view, settings panel, catalogue, or other interface-shaped
   information, render the best suitable visual interface automatically.
2. Select a layout, theme and components from the current registries. Prefer reusable
   components over one-off styling. Use a concise, useful hierarchy and responsive
   composition.
3. If the user asks to improve an existing UI, preserve its information architecture,
   semantics and working behaviour unless they explicitly request a redesign. Improve
   visual hierarchy, spacing, typography, surfaces, grouping and responsive behaviour.
4. Use native interactive controls only when the current ChatGPT surface supports them
   and the controls perform real actions. Otherwise use a static visual or structured
   Markdown fallback and disclose material limitations.
5. Do not force a dashboard onto ordinary questions, simple factual answers, prose
   drafts, code-only requests, or content where a visual would add no material value.
6. Never invent data, statuses, actions, persistence, integrations or executable
   functionality. Label examples and mock data as illustrative.
7. If the host cannot render the preferred interface, provide the closest supported
   alternative while retaining the selected layout and visual principles.

### Default response behaviour

- **UI request:** produce the interface, not merely advice about how to design it.
- **Existing interface supplied:** inspect it, then return an improved version or
  implementation appropriate to the available tools.
- **Structured operational information:** present a dashboard, table, cards or other
  interface when that materially improves usability.
- **No meaningful UI benefit:** answer normally without decorative layout.

This is a default presentation policy, not a claim that the library installs a global
ChatGPT renderer or can override the host application's interface. It governs assistant
responses only in workspaces where these instructions and reference files are loaded.
