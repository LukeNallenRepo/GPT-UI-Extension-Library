# GPT UI Extension Library

**One library. Reusable interfaces. Built for AI.**

The GPT UI Extension Library is a portable design and instruction system that gives AI assistants a reusable vocabulary for building and improving interfaces. It contains design tokens, theme presets, component contracts, layouts, interaction patterns, application profiles and host-rendering guidance.

It is designed to help an assistant turn interface-shaped information into clearer dashboards, workspaces, analytics views, operational panels and other structured experiences—without rebuilding the design foundation for every project.

## The problem

AI-generated interfaces often repeat the same foundations: navigation, dashboards, cards, data visualisations, responsive layouts, interaction patterns and visual systems. Rebuilding these separately creates duplicated effort and inconsistent results.

## The solution

The library separates reusable design foundations from application-specific data and behaviour. An assistant can discover an existing theme, choose a layout, compose registered components and adapt the result to the capabilities of its host environment.

**Build interfaces by composing reusable systems, not reinventing them.**

## What it supports

- **Operations:** task queues, agent dashboards, workflow status, approvals and activity feeds.
- **Analytics:** KPI views, charts, comparisons, segments and data-quality indicators.
- **Projects:** workspaces, milestones, progress, documents and assignments.
- **Creative tools:** timelines, audio/visual displays, editing surfaces and property panels.
- **Application infrastructure:** navigation, responsive layouts, cards, forms, menus and themes.

## Automatic UI enhancement

When the library is mounted, automatic UI enhancement is enabled by default for relevant requests. If a user asks for or supplies interface-shaped content—such as a project status, file inventory, operational workflow, analytics report, task queue or existing dashboard—the assistant should choose an appropriate layout, theme and reusable components and render a suitable interface without requiring the user to request a dashboard explicitly.

This is an instruction-driven behaviour within the Project or GPT where the library is loaded. It does not modify ChatGPT globally, install executable components, or guarantee that every host supports interactive rendering. Ordinary answers and prose tasks should remain ordinary when a visual adds no value.

## Architecture

The library has three complementary layers:

1. **UI Extension Registry** — records interface capabilities, provenance and evidence status.
2. **Universal UI Component Library** — defines reusable components, layouts, widgets and interaction patterns.
3. **Visual Enhancement System** — provides themes, tokens, styling treatments and responsive presentation.

The documented logical import packages are `ui-core`, `ui-components`, `ui-visualisations`, `ui-workflows`, `ui-resources`, `ui-interactions` and `ui-themes`. These are architectural boundaries, not published npm packages.

## Current library snapshot

| Registry area | Documented count |
|---|---:|
| Component registry families | 18 |
| Component contracts | 32 |
| Theme presets | 7 |
| Layout patterns | 10 |
| Application profiles | 19 |

These are documentation/registry counts, not a claim that each entry is a separately implemented executable component. Consult evidence labels and host-adapter guidance.

## Install in ChatGPT

The simplest installation uses one Project source and one instruction block:

1. Download and extract this repository.
2. Create a ChatGPT Project.
3. Upload `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` as a Project source.
4. Paste the contents of `CHATGPT_INSTRUCTIONS.md` into Project settings → Project instructions.
5. Start a chat in the Project and send `Mount UI extension library`.
6. Test with: `Turn this project status into a polished responsive dashboard: 12 tasks, 8 complete, 3 active, 1 blocked.`

For a custom GPT, where the GPT editor is available, use the same instruction file in **Instructions** and the consolidated knowledge file under **Knowledge**. See [`CHATGPT_SETUP.md`](CHATGPT_SETUP.md) for the full steps, availability caveat and test prompts.

## Repository structure

- `INSTRUCT.md` — primary operating standard and default UI enhancement behaviour.
- `CHATGPT_INSTRUCTIONS.md` — copy/paste instructions for a ChatGPT Project or eligible GPT.
- `CHATGPT_SETUP.md` — installation and verification guide.
- `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` — consolidated single-file knowledge source for ChatGPT.
- `MOUNT_INSTRUCT.md` — mount and resume protocol.
- `UI_EXTENSION_ARCHITECTURE.md` — architecture and logical package boundaries.
- `UNIVERSAL_COMPONENT_REGISTRY.md` and `02_COMPONENT_LIBRARY/` — component catalogues and contracts.
- `01_DESIGN_SYSTEM/` — tokens and theme presets.
- `LAYOUT_REGISTRY.md` — responsive layout patterns.
- `09_IMPLEMENTATION/` — ChatGPT adapter and renderer guidance.
- `12_APP_PROFILES/` — application-specific examples; generic components remain domain-neutral.
- `archive/legacy/` — historical working drafts, not active instructions.

## Important portability boundary

The archive provides specifications and instructions. It does not install executable React components, create a runtime, transfer account memory, grant connector permissions, deploy an app, or synchronise changes between accounts. The destination assistant must be given the knowledge file and instructions, and actual rendering depends on the capabilities of that ChatGPT surface.

## Licence

Copyright © 2026 Luke Nallen. This repository is distributed under the custom **Free Use, Modification and Non-Sale Licence** in [`LICENSE.md`](LICENSE.md). It permits use, modification and free redistribution under its conditions, including use within wider commercial projects, but prohibits selling the library or modified material or charging for access or distribution. It is not the standard MIT License and is not an OSI-approved open-source licence.

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md). Keep generic components domain-neutral, preserve evidence labels, update both registries when contracts change, and document significant modifications.

---

**Reusable interfaces. Composable applications. Visual-first AI.**
a
