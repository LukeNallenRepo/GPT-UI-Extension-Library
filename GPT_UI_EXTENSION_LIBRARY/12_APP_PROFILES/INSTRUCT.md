---
author: "Luke Nallen"
---

# Generic Application Profiles

## Purpose
This directory contains reusable, product-neutral application archetypes. Profiles describe common interface structures and user tasks; they are not tied to a named product, repository, brand, data source, framework, or external tool.

## Profile rules
- Use a profile as a starting composition, never as a fixed product specification.
- Replace example labels and data with the host application's actual information.
- Keep application name, logo, brand tokens, domain language, business logic, data schemas, integrations and permissions in the host application's own configuration.
- Do not require another library, agent, framework, service, repository, or shared master directory to use a profile.
- Select a profile by user task and information architecture. Select a theme independently from `01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`.
- Combine profiles when an application spans multiple tasks; avoid duplicating components.
- Mark unknown fields as `Not supplied` or omit them. Never invent integrations, capabilities or data.
- Adapt all layouts to the host's supported rendering capabilities and responsive constraints.

## Standard profile contract
Each profile defines: purpose, suitable use cases, information hierarchy, suggested navigation, screen regions, reusable component families, interaction states, data inputs (descriptive only), responsive behaviour, accessibility requirements, theme options and host integration boundary.

## Included generic profiles
- `GENERAL_APPLICATION_PROFILE.md` — general-purpose SaaS and product interface.
- `DATA_WORKBENCH_PROFILE.md` — analytics, monitoring and data exploration.
- `CREATIVE_STUDIO_PROFILE.md` — creative production and editing.
- `EDITORIAL_CONTENT_PROFILE.md` — reading, writing, publishing and documentation.
- `OPERATIONS_WORKSPACE_PROFILE.md` — tasks, workflows, approvals and operational control.
- `PROJECT_WORKSPACE_PROFILE.md` — project planning, milestones and collaboration.
- `RESOURCE_LIBRARY_PROFILE.md` — searchable files, assets and knowledge collections.
- `COMMERCE_EXPERIENCE_PROFILE.md` — product discovery, catalogues and purchasing journeys.

These are reusable design patterns, not executable applications or bundled backend services.
