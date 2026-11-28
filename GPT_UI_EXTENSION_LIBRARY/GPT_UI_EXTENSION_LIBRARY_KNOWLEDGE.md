# GPT UI Extension Library — Consolidated Knowledge Bundle

This standalone bundle is generated from canonical package files. Root `INSTRUCT.md` governs operating behaviour.


---

## SOURCE FILE: `APP_BUILDER_INSTRUCT.md`

```markdown
---
title: Universal App Builder Instructions
version: 1.0.0
updated: 2026-11-23
status: reusable-build-workflow
author: "Luke Nallen"
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
```


---

## SOURCE FILE: `CHANGELOG.md`

```markdown
---
author: "Luke Nallen"
---

# Changelog

All notable changes to the GPT UI Extension Library are documented here. Repository release version and library specification version are tracked separately.

## [1.1.0] - 2026-11-24

### GitHub release preparation
- Flattened the distributable archive so the repository contents sit directly under one root folder.
- Removed the nested ZIP that duplicated the repository.
- Removed the duplicated embedded-source repository snapshot; retained selected historical drafts under `archive/legacy/` with an explicit non-authoritative notice.
- Selected one canonical `README.md` and removed the duplicate `README_updated.md`.
- Added ChatGPT Project and custom GPT setup guidance.
- Added a copy/paste instruction file that enables automatic UI enhancement by default for relevant interface-shaped tasks.
- Added a consolidated Markdown knowledge bundle so users can install the reference library with one Project/GPT knowledge upload.
- Updated mount and resume procedures with behaviour checks and explicit portability boundaries.
- Retained the existing custom Free Use, Modification and Non-Sale Licence without changing its terms.

### Validation
- JSON syntax, Markdown link targets, required release files, archive structure and ZIP integrity checked.
- Installation sequence simulated against the documented ChatGPT Project/GPT configuration.
- A live installation in a separate ChatGPT account was not performed; see `RELEASE_VALIDATION.md`.


## 2.4.0 — 2026-11-28

- Replaced product-specific application profiles with eight reusable, domain-neutral application archetypes.
- Removed the application inventory tied to an external ecosystem and replaced it with a generic profile index.
- Removed the nested distribution archive and legacy app-specific profile material from the standalone package.
- Added explicit standalone dependency rules: no A.I Master or related tool is required.
- Added automatic mount/reload behaviour for every upload, replacement and update, with a repeated bordered status indicator on every successful mount.
- Expanded ChatGPT workspace instructions for consistent visual presentation across conversations where the library is installed, while preserving normal answers when a UI adds no value.
- Confirmed the six requested core themes and retained Neon Dark as an optional additional preset.
- Regenerated the consolidated knowledge bundle from the standalone package.


## 2.5.0 — 2026-11-28

### Conversation-history expansion
- Added a universal pattern catalogue covering application, data, agent/workflow, knowledge, creative, commerce, learning and interface-state patterns.
- Added domain interface blueprints derived from available prior conversations: Karma Circle/Behaviour OS, Ascension Research, Genesis/AgentMaster, Questmaster, File Warden, LocalForge, BookMaster and Pizza Hub.
- Added framework/design-system ingestion specification for user-supplied Bootstrap, React, Tailwind, shadcn/ui, Material UI, Ant Design and custom systems.
- Added normalized ingestion manifest requirements, dependency/compatibility checks, project-level selection and license/provenance preservation.
- Added extended contracts for graph exploration, scenario simulation, evidence, workflow execution, library management, publishing and commerce operations.
- Added accessibility/responsive standards and reusable example compositions.
- Expanded component registry and regenerated consolidated knowledge bundle.

### Scope
- Conversation-derived material is generalized into reusable patterns while preserving source terminology.
- This release uses the available prior-conversation context and the uploaded 2.4.0 archive; it does not claim exhaustive retrieval of every historical chat or every attachment.
- No third-party framework runtime or executable app implementation is bundled by this documentation expansion.
```


---

## SOURCE FILE: `CHATGPT_INSTRUCTIONS.md`

```markdown
---
author: "Luke Nallen"
---

# GPT UI Extension Library — ChatGPT Operating Instructions

You have access to the standalone GPT UI Extension Library knowledge bundle. Follow its root `INSTRUCT.md`, component registry, theme presets, layout registry, generic application profiles and host adapters.

## Default behaviour: visual presentation ON

Apply the library's presentation standards to every response in this installed workspace: clear hierarchy, readable typography, consistent spacing, concise grouping and restrained visual emphasis.

Whenever the request or information can materially benefit from an interface, create the suitable interface automatically. Do not wait for the user to ask for a dashboard. Choose from dashboards, cards, tables, timelines, diagrams, forms, workflow views, resource lists and other registered patterns as appropriate.

Use a generic theme and reusable components. Keep the visual language consistent across conversations in this Project/GPT. Preserve the purpose, labels, information architecture, data and working behaviour of any supplied interface unless asked to change them.

Do not force a dashboard onto a simple factual answer, short exchange, prose draft or code-only task where a visual adds no value. Beautify those responses through clear formatting rather than decorative UI.

Use interactive controls only when the host supports them and they perform real actions. Otherwise provide a static or structured fallback. Never invent data, statuses, persistence, integrations, actions or executable functionality.

## Automatic mount

When the GPT UI Extension Library archive or folder is uploaded, treat the upload as a mount event. This applies to first uploads, repeated uploads, replacements and every updated version. Inspect the incoming root `INSTRUCT.md`, verify the package resources, and display the bordered status indicator `GPT UI EXTENSION LIBRARY: ACTIVE` on every successful mount. The library name is orange and ACTIVE green. Do not suppress the indicator because a previous version was mounted.

## Standalone boundary

The library does not require A.I Master or any of its tools. Do not reference external master paths or resolve mandatory resources outside the package. Host applications own their own data, business logic, authentication, persistence, integrations and permissions.

## Host limitation

These instructions affect only the Project, eligible custom GPT or assistant workspace in which they are installed and its available knowledge. They do not globally modify ChatGPT or other conversations. Rendering and interaction depend on the current host surface and supported capabilities.
```


---

## SOURCE FILE: `CHATGPT_SETUP.md`

```markdown
---
author: "Luke Nallen"
---

# Install in ChatGPT

This library is a portable set of instructions, registries, design specifications and examples. It is not a software plugin and does not install executable React components or change ChatGPT's global interface. It guides the assistant's responses inside the Project or GPT where it is loaded.

## Recommended: ChatGPT Project

1. Download `15_GPT_UI_extension_library.zip` from the GitHub repository and extract it.
2. In ChatGPT, create a new Project.
3. Upload `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` from the extracted folder as a Project source. This single consolidated file is designed to avoid multi-file upload limits.
4. Open the Project menu, choose **Project settings**, and paste the complete contents of `CHATGPT_INSTRUCTIONS.md` into Project instructions.
5. Start a new chat in the Project and send: `Mount UI extension library`.
6. Ask for a test, for example: `Turn this project status into a polished responsive dashboard: 12 tasks, 8 complete, 3 active, 1 blocked.`
7. Check that the assistant uses a suitable layout and theme, labels the supplied figures as user-provided, and does not claim that controls or persistence exist unless they do.

Project sources and Project instructions serve different purposes: the knowledge bundle supplies reference material; the instruction text establishes default behaviour. Keep both.

## Custom GPT (where creation or editing is available)

1. Open the GPT editor on the ChatGPT web experience, if your account and workspace currently permit GPT creation or editing.
2. Paste `CHATGPT_INSTRUCTIONS.md` into the GPT's **Instructions** field.
3. Upload `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` under **Knowledge**.
4. Save or update the GPT, then test it in Preview with the same sample request above.

Availability of GPT creation and publishing depends on current ChatGPT plan, workspace and product rules. If the GPT editor is unavailable, use the Project method.

## Quick verification prompts

- `Mount UI extension library` — should report the version, registries, themes, layouts and limitations it can actually inspect.
- `Make a dashboard from this status: 12 tasks, 8 complete, 3 active, 1 blocked.` — should create a clear dashboard and label the values as supplied by the user.
- `Improve this existing interface without changing its functionality: [paste interface]` — should preserve semantics and behaviour while improving presentation.
- `Explain photosynthesis in two sentences.` — should answer normally, not force a dashboard.

## What installation does and does not do

**It does:** provide a portable visual vocabulary, component contracts, themes, layouts, examples and response instructions to the selected Project or GPT.

**It does not:** install code, create a React runtime, add new native ChatGPT controls, grant access to external files or apps, transfer memory or permissions, or apply to chats outside the configured Project/GPT. Actual rendering depends on the capabilities of the ChatGPT surface and selected model.

## Updating

When a new release is published, replace the Project/GPT knowledge file with the new `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` and review the corresponding `CHATGPT_INSTRUCTIONS.md`. For a Project, update Project instructions as needed.
```


---

## SOURCE FILE: `CONTRIBUTING.md`

```markdown
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
```


---

## SOURCE FILE: `INSTRUCT.md`

```markdown
---
title: GPT UI Extension Library
version: 2.4.0
updated: 2026-11-28
status: portable-composable-ui-standard
author: "Luke Nallen"
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


## Standalone package and dependency boundary

This repository root is the complete GPT UI Extension Library package. It must remain independently usable when copied, uploaded, installed or mounted by itself.

- Do not require A.I Master, Agent Master, Genesis, Questmaster, File Warden, any other product, or any directory outside this package.
- Do not resolve profile, theme, component, instruction or knowledge resources from an external master path.
- All mandatory references must resolve within this package. Optional host integrations are adapters only and must never become installation prerequisites.
- Host applications provide their own data, business logic, authentication, persistence, APIs and permissions.
- Generic application profiles in `12_APP_PROFILES/` must not contain product-specific names, logos, paths, credentials, data schemas or integrations.

## Automatic mount on every upload, replacement and update

Uploading a file or archive clearly identified as GPT UI Extension Library is itself a mount/reload event. Do not wait for a separate mount command unless the user explicitly requests a file-only operation or says not to mount.

This rule applies every time, including:
- first upload;
- repeated upload of the same filename or version;
- updated or replacement archives;
- uploads that replace only `INSTRUCT.md` or other library resources;
- reloads and reinitialisations.

For each event:
1. Inspect the newly supplied package and identify its actual root.
2. Read the incoming root `INSTRUCT.md` first and apply that version's lifecycle instructions.
3. Verify that core instructions, registries, themes, layouts, profile templates and knowledge bundle are accessible.
4. Activate the incoming version only after inspection succeeds.
5. Display the status indicator below again on every successful mount event. Never suppress it because an earlier upload was mounted.

### Required mount status display

On every successful mount, display exactly one bordered status indicator:

`GPT UI EXTENSION LIBRARY: ACTIVE`

Render `GPT UI EXTENSION LIBRARY:` in orange and `ACTIVE` in green, enclosed together in one clearly visible border. Use the closest supported presentation if actual text colour or border styling is unavailable. Do not claim ACTIVE if the incoming package could not be inspected or loaded. Do not expose mount logs or diagnostic details unless the user asks or a failure requires explanation.

## Default presentation behaviour in every installed conversation

When these instructions and the library knowledge are loaded into a ChatGPT Project, eligible custom GPT, or another assistant workspace, apply the library's presentation standards to every response in that workspace:

- Beautify and structure responses with clear hierarchy, readable typography, concise grouping, consistent spacing and suitable visual emphasis.
- Whenever a user request or its content can materially benefit from a user interface, render a suitable interface automatically; do not wait for the user to request a dashboard.
- Use dashboards, cards, tables, timelines, diagrams, forms or other components when they improve comprehension or task completion.
- Apply a suitable generic theme and reusable components. Keep styling coherent across conversations in that installed workspace.
- Preserve plain prose for answers where a UI would add no value; do not force dashboards onto every simple answer.
- Do not fabricate data, statuses, integrations, persistence, actions or interactive functionality. Use only controls supported by the host and make fallbacks clear.

This policy operates only in conversations where the library's instructions and knowledge are actually installed or loaded. Uploading a ZIP does not globally modify ChatGPT, other chats, accounts, or the host application's native interface. Project/GPT instructions, available knowledge, model capabilities and host rendering support determine the scope.


## Expanded conversation-derived resources (2.5.0)

Consult these additional standalone directories when relevant:
- `13_PATTERN_LIBRARY/` — reusable interaction and composition patterns.
- `14_DOMAIN_INTERFACE_BLUEPRINTS/` — generalized blueprints derived from prior project conversations.
- `15_FRAMEWORK_ADAPTERS/` — user-supplied library ingestion, indexing, manifests and framework adapters.
- `16_COMPONENT_CONTRACTS/` — extended component contracts.
- `17_ACCESSIBILITY_RESPONSIVE/` — responsive and accessibility standards.
- `18_SOURCE_PROVENANCE/` — source-to-pattern traceability and scope.
- `19_EXAMPLES/` — reusable example compositions.

When using conversation-derived examples, retain the source-specific context and do not promote project-specific assumptions into universal rules. For user-provided UI libraries, follow the ingestion workflow and preserve license/provenance metadata.
```


---

## SOURCE FILE: `LAYOUT_REGISTRY.md`

```markdown
---
title: Universal Layout Registry
version: 1.0.0
updated: 2026-11-23
author: "Luke Nallen"
---

# Universal Layout Registry

Layouts define composition and responsive structure. They are independent of app domain and theme.

| Layout ID | Name | Composition | Best use |
|---|---|---|---|
| `layout.app-shell` | App Shell | Top bar, optional sidebar, content region | Full applications |
| `layout.command-centre` | Command Centre | Navigation rail, KPI grid, priority queue, activity | Operations and administration |
| `layout.analytics-overview` | Analytics Overview | Header, filters, KPI grid, charts, segments, data quality | Performance and reporting |
| `layout.project-workspace` | Project Workspace | Project header, completion panel, task/document cards, milestones, activity | Project tracking |
| `layout.creative-editor` | Creative Editor | Tool rail, main canvas, properties inspector, transport/timeline | Audio, visual and content creation |
| `layout.data-workbench` | Data Workbench | Query/filter rail, data canvas, inspector, results | Analysis and data operations |
| `layout.document-dashboard` | Document Dashboard | Document header, navigation, rendered source, contextual panels | Markdown and knowledge views |
| `layout.bento-dashboard` | Bento Dashboard | Responsive modular card grid | General dashboards |
| `layout.split-workspace` | Split Workspace | Resizable primary and secondary panes | Editors, file managers and inspectors |
| `layout.mobile-stack` | Mobile Stack | Single-column ordered sections, bottom navigation where needed | Narrow mobile interfaces |

## Responsive rules

- Mobile: collapse sidebars to a drawer or bottom navigation; use one-column cards; keep primary actions reachable; prevent page-level horizontal overflow.
- Tablet: use a compact rail and two-column cards where content permits.
- Desktop: allow persistent sidebars, wider grids and split panes; preserve a readable maximum content width.
- Reflow by available width, not device labels alone.
- Do not hide critical information on mobile; move it into accessible disclosure or secondary panels.

## Layout composition contracts

### Command Centre
`AppShell + PageHeader + KPIGrid + PriorityQueue + ActivityFeed`

Optional: `AgentRoster`, `TriggerList`, `NotificationCenter`, `TaskTable`.

### Analytics Overview
`DashboardFrame + FilterBar + KPIGrid + ChartPanel + SegmentBreakdown + DataQualityCard`

Optional: `ComparisonCard`, `DataTable`, `InsightCallout`.

### Project Workspace
`ProjectHeader + ProgressCard + ResourceCardGrid + MilestoneList + ActivityFeed`

Optional: `TaskBoard`, `DocumentList`, `DependencyMap`, `AgentAssignmentPanel`.

### Creative Editor
`EditorShell + ToolRail + MainCanvas + Timeline/AudioVisualizer + PropertiesPanel`

Optional: `LayerList`, `TransportControls`, `AssetBrowser`, `PresetBrowser`.

### Document Dashboard
`DashboardFrame + PageHeader + DocumentNavigation + MarkdownDocumentRenderer + RelatedResources`

Optional: `MetricTile`, `Callout`, `DataTable`, `ReadOnlyBanner`.


## Additional reusable compositions (2.5.0)

| Layout ID | Name | Composition | Best use |
|---|---|---|---|
| `layout.research-operations` | Research Operations | Stage board, evidence ledger, review queue, release checklist | Research pipelines |
| `layout.agent-orchestration` | Agent Orchestration | Agent roster, workflow canvas, task manifest, execution timeline | Agent/workflow systems |
| `layout.model-explorer` | Interactive Model Explorer | Network canvas, node inspector, scenario workbench, comparison | Graph and simulation interfaces |
| `layout.library-manager` | Component Library Manager | Importer, component picker, theme picker, dependency report | Design-system ingestion |
| `layout.publishing-workspace` | Publishing Workspace | Chapter navigator, editor, issue list, revision history | Books and long-form publishing |
| `layout.service-operations` | Service Operations | Orders, inventory, location comparison, exceptions | Multi-location services and commerce |
```


---

## SOURCE FILE: `LICENSE.md`

```markdown
---
author: "Luke Nallen"
---

GPT UI EXTENSION LIBRARY FREE USE, MODIFICATION AND NON-SALE LICENCE

Copyright (c) 2026 Luke Nallen.

DEFINITIONS

"Material" means the files, documentation, specifications, designs, component definitions, examples and other content distributed as part of the GPT UI Extension Library.

"Modified Material" means any adaptation, modification, translation, extension or derivative work based on or incorporating the Material.

PERMISSION GRANT

Subject to the conditions in this licence, Luke Nallen grants you a worldwide, perpetual, royalty-free, non-exclusive permission to:

use the Material for personal, educational, research and commercial project purposes;
copy and reproduce the Material;
modify, adapt and create Modified Material;
publish and redistribute the Material and Modified Material; and
permit others to exercise these same permissions under this licence.

You may use the Material as part of a commercial project or service, provided that the Material and Modified Material are not themselves sold or supplied for a fee in breach of Section 3.

NON-SALE AND NO-FEE CONDITIONS

You must not:

sell the Material, in whole or in part;
sell Modified Material, in whole or in part;
charge a purchase price, licence fee, subscription fee, access fee, download fee, distribution fee or other fee for the Material or Modified Material themselves;
make access to the Material or Modified Material conditional on payment; or
bundle the Material or Modified Material into a product, package or download where a fee is charged for access to or distribution of that Material or Modified Material.

For clarity, this section does not prohibit earning money from a wider commercial project, product or service that uses the Material, provided the Material or Modified Material is not itself sold, separately monetised, or distributed behind a paid access or distribution charge.

REDISTRIBUTION CONDITIONS

When you publish, share or redistribute the Material or Modified Material, you must:

include a complete copy of this licence;
retain all existing copyright and attribution notices;
identify significant changes where reasonably practical; and
make clear that your Modified Material is modified and is not an official release by Luke Nallen unless you have written permission to say otherwise.

You must not remove, obscure or alter the copyright attribution or the non-sale conditions in this licence.

NO ADDITIONAL RESTRICTIONS

You may not impose additional terms that prevent recipients from exercising the permissions granted by this licence. Any redistribution of the Material or Modified Material must remain subject to the non-sale and attribution conditions in this licence.

THIRD-PARTY MATERIAL

This licence applies only to Material for which Luke Nallen has the rights to grant these permissions. Third-party software, fonts, icons, images, names, logos, trademarks and other assets may be subject to separate licences or terms. You are responsible for complying with those separate terms.

TERMINATION

The permissions granted under this licence terminate automatically if you fail to comply with its conditions. They may be reinstated if the rights holder expressly agrees in writing.

DISCLAIMER OF WARRANTY AND LIABILITY

The Material is provided "AS IS", without warranty of any kind, express or implied, including but not limited to warranties of merchantability, fitness for a particular purpose and non-infringement, to the maximum extent permitted by applicable law.

In no event shall the rights holder be liable for any claim, damages or other liability arising from, out of or in connection with the Material or its use, to the maximum extent permitted by applicable law.

LICENCE CHARACTER

This is a custom free-use, modification and non-sale licence. It is not the standard MIT License and is not an OSI-approved open-source licence. The restriction on selling or charging for distribution means the Material does not meet the standard Open Source Definition.

For permissions beyond these terms, contact the rights holder.

END OF LICENCE
```


---

## SOURCE FILE: `MOUNT_INSTRUCT.md`

```markdown
---
author: "Luke Nallen"
---

# Mount and Resume Instructions

## Automatic mount trigger

Every upload of a package clearly identified as GPT UI Extension Library is a mount/reload event. Mount automatically on first upload, repeated uploads, replacements, updated versions and instruction-only updates. Do not wait for a separate command unless the user explicitly requests a file-only edit or says not to mount.

## Mandatory procedure

1. Inspect the incoming archive/folder and identify the actual package root.
2. Read the incoming root `INSTRUCT.md` first.
3. Verify access to the knowledge bundle, component registry, design system and theme presets, layout registry, generic app profiles and host adapters.
4. Activate the incoming version only after successful inspection.
5. Display the required status indicator on every successful mount, even if the same version was previously active.

## Required status indicator

Display this bordered indicator after every successful mount:

**GPT UI EXTENSION LIBRARY:** **ACTIVE**

The library name must be orange and `ACTIVE` green. Enclose both segments together in one visible border. Use the closest supported presentation if colour styling is unavailable. Do not display ACTIVE after a failed or incomplete mount. Do not add a gate, logs, file lists or a diagnostic report unless explicitly requested or needed to explain a failure.

## Mount scope and limits

The package is standalone. Do not require A.I Master or any external product, agent, tool, repository, directory, account memory or connector.

Mounting makes the supplied instructions and reference resources available in the current supported workspace; it does not install executable software or grant permissions. For ongoing automatic UI behaviour in a Project or eligible custom GPT, install `CHATGPT_INSTRUCTIONS.md` and make `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` available as knowledge. The behaviour applies only in that configured workspace, not globally across ChatGPT.

## Resume

When the user says `resume UI library`, `use mounted UI library`, or requests an interface:
- consult the relevant component, theme, layout and generic profile contracts;
- reuse existing components before inventing new ones;
- preserve supplied data, meaning and working behaviour;
- render the strongest interface supported by the host;
- disclose material host limitations and use a structured fallback where necessary.
```


---

## SOURCE FILE: `README.md`

```markdown
---
author: "Luke Nallen"
---

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

This package has no mandatory dependency on A.I Master, Agent Master, Genesis, Questmaster, File Warden, any other product, or any external repository. Host applications provide their own data, business rules, integrations, authentication and permissions.

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
```


---

## SOURCE FILE: `RELEASE_VALIDATION.md`

```markdown
---
author: "Luke Nallen"
---

# Release Validation Report

**Validation date:** 2026-11-28  
**Package version:** 2.4.0  
**Package:** `05_GPT_UI_EXTENSION_LIBRARY.zip`

## Results

| Check | Result | Evidence / scope |
|---|---|---|
| Source archive access | PASS | Incoming AI Master archive opened and source library extracted. |
| Standalone root layout | PASS | Library contents placed directly at package root; no AI Master directory prefix. |
| External master dependencies | PASS | No mandatory references to AI Master paths or external master directories remain. |
| App profile decoupling | PASS | Product-specific profile files replaced with eight generic archetypes. |
| Generic profile boundaries | PASS | Profiles specify presentation only; host applications own data, logic, authentication, persistence and integrations. |
| Theme coverage | PASS | Six requested core themes present; Neon Dark retained as optional preset. |
| Automatic mount instructions | PASS | Every upload, replacement and update triggers a fresh mount procedure and repeated status display. |
| ChatGPT conversation styling | PASS — INSTRUCTION REVIEW | Workspace instructions apply consistent visual presentation and automatic UI selection where useful. |
| JSON syntax | PASS | Theme presets, component registry and generic app inventory parse successfully. |
| Relative Markdown links | PASS | All local Markdown links resolve within the package. |
| Consolidated knowledge bundle | PASS | Regenerated from current canonical package files. |
| ZIP integrity | PASS | Output archive reopened and CRC-tested. |

## Generic application profiles

Eight profiles are included:

1. General Application
2. Data Workbench
3. Creative Studio
4. Editorial Content
5. Operations Workspace
6. Project Workspace
7. Resource Library
8. Commerce Experience

## Theme presets

Core themes: Data Workbench, Neutral Product, Creative Studio, Warm Editorial, High Contrast and Light Product. Optional additional preset: Neon Dark.

## Important scope limitations

This is a standalone instruction, design-system and component-specification package. It does not bundle an executable ChatGPT plugin, application backend, framework runtime or external integration.

Automatic UI presentation applies only in a ChatGPT Project, eligible custom GPT or other workspace where the instructions and knowledge are installed and available. Uploading the archive does not globally modify ChatGPT or other conversations. Actual interactive rendering depends on host capabilities.

The status indicator is a required assistant response on every successful mount event; it is not a background installation daemon.


## 2.5.0 expansion checks

| Check | Result | Scope |
|---|---|---|
| Conversation-derived resource index | PASS | Available prior context indexed with explicit scope note |
| Pattern catalogue | PASS | Added reusable cross-domain UI patterns |
| Domain blueprints | PASS | Added project-derived examples without bundling app data |
| Framework ingestion specification | PASS | Bootstrap, React, Tailwind, shadcn/ui, Material UI, Ant Design and custom systems |
| Component registry | PASS | JSON parsed after expansion |
| Standalone boundaries | PASS | No runtime or external master dependency introduced |
| Provenance/licensing guidance | PASS | Source and license retention requirements documented |

Historical chat retrieval is not guaranteed exhaustive; the provenance index records the source material available for this release.
```


---

## SOURCE FILE: `UI_EXTENSION_ARCHITECTURE.md`

```markdown
---
title: UI Extension Architecture and Import Map
version: 1.0.0
updated: 2026-11-23
status: integrated-library-specification
author: "Luke Nallen"
---

# UI Extension Architecture and Import Map

## 1. Purpose

Create a **portable, reusable UI extension library** containing interface capabilities, visual components, interaction patterns and design systems developed across GPT applications. The library consolidates three complementary layers:

1. **UI Extension Registry** — the inventory of interface capabilities developed or used across existing GPT apps, including provenance and implementation status.
2. **Universal UI Component Library** — reusable components, layouts, widgets and interaction patterns.
3. **Visual Enhancement System** — styling, animation, lighting, depth, transitions and responsive presentation.

These are architectural layers, not three separate competing registries. The registry records what exists; the component library defines reusable contracts; the visual enhancement system provides themes and reusable presentation treatments.

## 2. Import architecture

The library is organised into independently consumable logical packages. The folders remain the canonical source tree; package names describe import boundaries and do not imply that published npm packages or executable builds already exist.

| Logical package | Responsibility | Canonical source |
|---|---|---|
| `ui-core` | Design tokens, typography, icon conventions, theme primitives and shared foundations | `01_DESIGN_SYSTEM/` |
| `ui-components` | Reusable visual and functional components | `02_COMPONENT_LIBRARY/` |
| `ui-visualisations` | Graphs, simulations, gauges, charts and analytical displays | `02_COMPONENT_LIBRARY/`, `UNIVERSAL_COMPONENT_REGISTRY.md` |
| `ui-workflows` | Agents, tasks, triggers, approvals, execution and automation interfaces | `02_COMPONENT_LIBRARY/`, app profiles |
| `ui-resources` | File management, metadata, provenance, registries, search and knowledge resources | `02_COMPONENT_LIBRARY/`, `03_APP_LIBRARY/` |
| `ui-interactions` | Modals, menus, controls, forms, notifications and interaction patterns | `05_INTERACTION_DESIGN/`, `02_COMPONENT_LIBRARY/` |
| `ui-themes` | Reusable visual identities and project-specific brand overrides | `01_DESIGN_SYSTEM/THEME_PRESETS/`, `07_VISUAL_DESIGN/`, `12_APP_PROFILES/` |

### Import rules

- A consumer may select only the packages it needs, while `ui-core` is the shared foundation.
- Package boundaries are dependency boundaries: higher-level packages may depend on `ui-core`; `ui-core` must not depend on app profiles or workflow-specific components.
- Keep data models and business logic in the host application. Components accept documented inputs and emit documented events.
- Keep app logos, names, brand assets and product-specific overrides outside generic component definitions.
- Reuse a component contract before creating a new one. Register new reusable components in both `UNIVERSAL_COMPONENT_REGISTRY.md` and `02_COMPONENT_LIBRARY/component_registry.json`.
- Mark each component as documented, proposed or implementation-verified. A registry entry is not proof of executable implementation.

## 3. Reusable component catalogue

The following catalogue is the shared capability taxonomy. Detailed props, events, states, accessibility and responsive contracts belong in the component catalogue and relevant design/interaction instructions.

### A. Navigation and application structure

- Dynamic application header.
- Sidebar navigation.
- Collapsible navigation groups.
- Multi-tab workspace.
- Breadcrumb navigation.
- Project switcher.
- Agent switcher.
- Command palette.
- Contextual action menus.
- Notifications and activity feed.
- Version and synchronisation indicators.
- Modal and drawer interfaces.

### B. Dashboard and information components

- Metric cards.
- KPI indicators.
- Progress bars and circular progress.
- Status badges.
- Activity timelines.
- Data tables.
- Searchable resource lists.
- Filter and sorting controls.
- Expandable information panels.
- Dashboard grids.
- Comparison panels.
- System health indicators.

### C. Visualisation components

- Interactive node graphs.
- Circular relationship diagrams.
- Network maps.
- Behavioural feedback loops.
- State transition visualisers.
- Probability distributions.
- Resonance/Dissonance gauges.
- Trajectory projections.
- Heatmaps.
- Time-series charts.
- Waveform displays.
- Audio spectrum visualisers.
- Hierarchical tree diagrams.

### D. Agent and automation components

- Agent profile cards.
- Agent status indicators.
- Role assignment panels.
- Trigger configuration.
- Task queues.
- Execution logs.
- Workflow visualisers.
- Agent communication streams.
- Approval interfaces.
- Error and retry panels.
- Batch execution controls.
- Weekly task manifests.

### E. Resource and knowledge components

- File explorer.
- Resource registry.
- Metadata editor.
- Version history.
- Provenance viewer.
- Document preview.
- Import/export controls.
- Dependency visualiser.
- Knowledge graph.
- Search and retrieval interface.
- Resource validation panel.

### F. Interactive application components

- Simulation controls.
- Scenario configuration.
- Interactive questionnaires.
- Reflection journal.
- Achievement systems.
- Quest interfaces.
- Challenge cards.
- Audio players.
- Waveform controls.
- Interactive maps and nodes.
- Real-time output panels.

## 4. Visual enhancement system

The source visual direction is available as a reusable **Neon Dark** treatment, not a mandatory global style. Apply it through theme tokens and optional component treatments.

| Element | Recommended treatment |
|---|---|
| Background | Deep black, charcoal and dark navy |
| Primary lighting | Electric violet and cyan |
| Secondary lighting | Magenta, blue and restrained orange |
| Cards | Layered translucent dark surfaces |
| Borders | Fine neon outlines and subtle gradients |
| Typography | Modern geometric sans-serif |
| Icons | Consistent Lucide-style iconography |
| Graphs | Glowing nodes, connecting lines and animated states |
| Transitions | Smooth movement and opacity transitions |
| Depth | Layered surfaces, shadows and controlled glow |

### Visual treatment constraints

- Preserve legibility, contrast and accessible focus states; glow must never reduce text clarity.
- Use translucency only with an opaque fallback.
- Respect reduced-motion preferences; animation is optional and must not carry essential information alone.
- Keep neon accents selective: active states, primary actions and meaningful visualisation signals.
- Use semantic tokens rather than hard-coded colours in components.
- App-specific visual identity is applied as a small override layer on top of a generic preset.

## 5. Relationship to existing library areas

| Architecture layer | Existing library areas |
|---|---|
| UI Extension Registry | `UNIVERSAL_COMPONENT_REGISTRY.md`, `02_COMPONENT_LIBRARY/component_registry.json`, `03_APP_LIBRARY/` |
| Universal UI Component Library | `02_COMPONENT_LIBRARY/`, `LAYOUT_REGISTRY.md`, `08_UX_ARCHITECTURE/` |
| Visual Enhancement System | `01_DESIGN_SYSTEM/`, `05_INTERACTION_DESIGN/`, `06_RESPONSIVE_DESIGN/`, `07_VISUAL_DESIGN/` |
| Import and portability guidance | `MOUNT_INSTRUCT.md`, `APP_BUILDER_INSTRUCT.md` |

## 6. Source coverage and verification

The supplied source notes identify Karma Circle and Behaviour OS as having the most developed documented component histories. Genesis and Warden have substantial workflow requirements, while their complete implemented UI component sets require verification.

Treat this as a documentation coverage statement, not a claim that all listed components are implemented. Preserve evidence labels and verify source code before upgrading a component to `IMPLEMENTATION-VERIFIED`.

## 7. Source records

The original OCR transcriptions are retained as source records:

- `ui_extensions_revision.md`
- `ui_extensions_revision2.md`

This integrated document consolidates their architecture, package boundaries, catalogue and visual direction. The source records are retained for traceability; this document and the two registries are the operational references.
```


---

## SOURCE FILE: `UNIVERSAL_COMPONENT_REGISTRY.md`

```markdown
---
author: "Luke Nallen"
---

# Universal GPT App UI Extension Registry

**Version:** 2.1\
**Compiled:** 2026-11-14\
**Purpose:** Portable, app-agnostic inventory and implementation specification for reusable UI components, theme presets and style primitives across unrelated applications.

## 1. Scope and evidence status

This registry consolidates UI capabilities documented in available
project history. It is an integration inventory, not proof that every
listed component has been implemented or shipped. The Karma Circle and
Behaviour OS have the strongest documented component inventories.
Genesis Forge, Questmaster and Warden have documented workflow
requirements, but their complete implemented UI sets require source-code
verification.

Status labels: - **Documented:** explicitly present in prior project
descriptions or architecture. - **Workflow-derived:** interface
component inferred from a documented workflow requirement;
implementation not verified. - **Proposed:** reusable enhancement
recommended for the shared library.

## 2. Application inventory

### The Karma Circle --- Documented

-   Application header, logo, navigation tabs, synchronisation
    indicator, version badge and close action.
-   Framework information cards.
-   18-node KC-MV24 Karma Circle visualiser.
-   Simulator and scenario controls.
-   Probability weighting.
-   Resonance engine and Resonance/Dissonance indicators.
-   Trajectory forecasts.
-   Insight engine and intervention engine.
-   Attention drivers and perception/behaviour insights.
-   Achievements, Karma Score, daily challenges and identity paths.
-   Quest system, identity vector and reflection journal.

### Behaviour OS --- Documented / Proposed modules

-   Core Loop.
-   State Analysis.
-   Intervention.
-   Gamification.
-   Simulation.
-   Behaviour/perception arcs.
-   Current State → Intervention → Projected Outcome flow.
-   Resonance, Dissonance, Emotional Resonance, confidence and likely
    trajectory indicators.
-   Modular, independently movable and crop/overlay-friendly panels.

### Genesis Forge --- Workflow-derived

-   Natural-language project creation entry point.
-   Project creation, agent creation and skill creation workflows.
-   Project workspace and project overview.
-   Knowledge reconstruction/import workflow.
-   Source/provenance review and project index.
-   Agent and skill catalogue.
-   Import progress, validation results and unresolved-source panels.

### Questmaster --- Workflow-derived

-   Weekly task manifest and weekly output view.
-   Individual task queue under `/tasks`.
-   Agent role and assignment cards.
-   Activation trigger definitions and status.
-   Batch execution view.
-   Task status, dependencies, outputs and blockers.
-   Execution summary and handoff report.
-   Distinguish the weekly executable manifest from standalone
    individual tasks.

### Warden --- Workflow-derived

-   Incoming resource intake queue for files downloaded or imported from
    GPTs and other AI systems.
-   Resource type and project identification.
-   Metadata extraction and validation.
-   Canonical naming preview and approval.
-   Version and provenance management.
-   Canonical destination selection.
-   Global resource registry and project index updates.
-   Reference repair/update report.
-   Duplicate detection and conflict resolution.

### LocalForge --- Documented project architecture

-   Code editor.
-   File explorer and project navigation.
-   Terminal / command execution panel.
-   Run and stop controls.
-   Application preview.
-   Backend/API status panel.
-   File read/write and project status workflows.
-   Known project architecture: React + Vite + TypeScript, with a Node
    backend and endpoints for files, status and execution.

### Lucifer's Language / THE GAME --- Conceptual and workflow-derived

-   Audio player and playback controls.
-   Waveform and audio-pattern visualiser.
-   Symbol/glyph display.
-   Clue and puzzle panels.
-   Interactive discovery sequence.
-   Player progress and participation state.
-   Shared narrative / world-state display.
-   Keep experimental audio claims distinct from fictional or ARG
    presentation.

## 3. Universal component catalogue

### Navigation and application shell

-   `AppShell`
-   `AppHeader`
-   `NavigationLink`
-   `Sidebar`
-   `NavigationGroup`
-   `Breadcrumbs`
-   `ProjectSwitcher`
-   `WorkspaceTabs`
-   `CommandPalette`
-   `ContextMenu`
-   `NotificationCenter`
-   `ActivityFeed`
-   `VersionIndicator`
-   `SyncStatus`

### Dashboard and information

-   `DashboardGrid`
-   `DashboardFrame`
-   `Callout`
-   `ReadOnlyBanner`
-   `MetricCard`
-   `KpiCard`
-   `StatusBadge`
-   `ProgressBar`
-   `CircularProgress`
-   `Timeline`
-   `DataTable`
-   `SearchableList`
-   `FilterBar`
-   `SortControl`
-   `ExpandablePanel`
-   `ComparisonPanel`
-   `SystemHealthCard`

### Visualisation

-   `NodeGraph`
-   `RelationshipCircle`
-   `NetworkGraph`
-   `FeedbackLoop`
-   `StateTransition`
-   `ProbabilityDistribution`
-   `ResonanceGauge`
-   `TrajectoryChart`
-   `Heatmap`
-   `TimeSeriesChart`
-   `Waveform`
-   `AudioSpectrum`
-   `HierarchyTree`

### Agents and workflows

-   `AgentCard`
-   `AgentStatus`
-   `RoleAssignment`
-   `TriggerEditor`
-   `TaskQueue`
-   `TaskManifest`
-   `ExecutionLog`
-   `WorkflowCanvas`
-   `CommunicationStream`
-   `ApprovalPanel`
-   `RetryPanel`
-   `BatchRunControls`
-   `WeeklyReport`

### Resources and knowledge

-   `FileExplorer`
-   `ResourceRegistry`
-   `MetadataEditor`
-   `VersionHistory`
-   `ProvenanceViewer`
-   `DocumentPreview`
-   `MarkdownDocumentRenderer`
-   `MarkdownDashboardRenderer`
-   `ImportExport`
-   `DependencyGraph`
-   `KnowledgeGraph`
-   `SearchResults`
-   `ValidationPanel`
-   `NamingPreview`

### Interactive experiences

-   `SimulationControls`
-   `ScenarioBuilder`
-   `Questionnaire`
-   `ReflectionJournal`
-   `AchievementCard`
-   `QuestCard`
-   `ChallengeCard`
-   `AudioPlayer`
-   `WaveformControls`
-   `InteractiveNode`
-   `LiveOutputPanel`

### Document-led dashboard composition

- `DashboardFrame` constrains and spaces a document-led dashboard.
- `Callout` presents semantic notices and contextual information.
- `NavigationLink` is a real, accessible destination link.
- `ReadOnlyBanner` discloses non-mutating view behaviour.
- `MarkdownDocumentRenderer` renders a canonical Markdown source using the host-native parser and link resolver.
- `MarkdownDashboardRenderer` composes the document renderer with dashboard primitives.

These components reuse existing `PageHeader`, `SectionHeader`, `MetricTile`, `StatusPill`, `Alert`, `Accordion`, `DataTable`, `EmptyState` and `ErrorState` rather than duplicating them. See `09_IMPLEMENTATION/markdown_dashboard_renderer.md` for the renderer contract.

## 4. Shared visual design system

### Base visual language

-   Dark backgrounds: near-black, charcoal and deep navy.
-   Primary accents: electric violet and cyan.
-   Secondary accents: magenta, blue and restrained orange.
-   Cards: layered dark surfaces, subtle translucency and clear
    hierarchy.
-   Borders: fine outlines, restrained gradients and controlled glow.
-   Typography: readable geometric sans-serif; use display typography
    sparingly.
-   Icons: one consistent icon family and stroke weight.
-   Motion: purposeful transitions, state changes and feedback; respect
    reduced-motion preferences.
-   Layout: responsive grids, resizable panels where useful, consistent
    spacing and alignment.
-   Accessibility: readable contrast, keyboard navigation, visible
    focus, semantic labels and non-colour status indicators.

### Reusable theme architecture

Themes are generic presets, not app-specific packages. Use `01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json` as the canonical catalogue. Any app may select a preset and apply a thin brand override. Do not create a new theme just because an app has a different name or logo.

Reusable visual treatments are documented in `02_COMPONENT_LIBRARY/STYLE_COMPONENTS/INSTRUCT.md`. App profiles record how shared presets and style components are composed; they do not own the shared theme definitions.

### Brand asset rule

Canonical logos, sigils and approved source artwork must be stored as
independent assets. Do not redraw or distort them as part of ordinary
component styling. Glow, blur, gradients and decorative framing should
be separate layers.

## 5. Recommended implementation architecture

Use a framework-independent component specification, with a React
implementation as the first adapter.

``` text
ui-extension-library/
  registry/
    extensions.json
    components.json
    themes.json
  core/
    tokens/
    typography/
    icons/
    motion/
    accessibility/
  components/
    navigation/
    dashboard/
    data-visualisation/
    agents/
    workflows/
    resources/
    interactive/
  layouts/
    app-shell/
    dashboard/
    workspace/
    split-pane/
  themes/
    ascension/
    karma-circle/
    behaviour-os/
    lucifers-language/
    the-game/
    operations/
  adapters/
    react/
    web-components/
  examples/
    karma-circle/
    behaviour-os/
    genesis-forge/
    questmaster/
    warden/
    localforge/
    lucifers-language/
```

Suggested React foundation, based on the existing Karma Circle
architecture: - React + TypeScript + Vite. - Tailwind CSS for utility
styling and theme tokens. - Framer Motion for optional motion. - Zustand
for shared client state where needed. - React Router for application
navigation. - Lucide icons. - Recharts for conventional charts;
specialised graph/audio components should use suitable dedicated
renderers.

These are recommended shared-library choices, not a claim that every
existing GPT app already uses this exact stack.

## 6. Extension contract

Each extension should declare: - Stable extension ID and semantic
version. - Display name and description. - Component exports. - Required
and optional dependencies. - Accepted properties and events. - State
ownership and persistence requirements. - Theme tokens consumed. -
Accessibility behaviour. - Responsive behaviour. - Data input/output
contract. - Permissions, if any. - Example usage and test coverage.

Example manifest:

``` json
{
  "id": "visualisation.resonance-gauge",
  "name": "Resonance Gauge",
  "version": "1.0.0",
  "category": "data-visualisation",
  "status": "documented-design",
  "framework": "react",
  "exports": ["ResonanceGauge"],
  "themeTokens": [
    "surface.panel",
    "accent.primary",
    "status.positive",
    "status.warning"
  ],
  "accessibility": {
    "keyboard": true,
    "textAlternative": true,
    "colourIndependentStatus": true
  }
}
```

## 7. Import and integration principles

1.  Import the shared tokens and component package before importing
    application-specific components.
2.  Keep business logic and domain models outside the presentation
    layer.
3.  Give every component typed inputs and documented outputs.
4.  Allow themes to change appearance without changing component
    behaviour.
5.  Keep components independently reusable and composable.
6.  Use adapters for framework-specific implementations.
7.  Version components independently where practical.
8.  Avoid duplicating components that already exist in the registry.
9.  Preserve source provenance and identify whether an extension is
    documented, workflow-derived, proposed or implementation-verified.
10. Validate imports, dependencies, accessibility and responsive
    behaviour in the target application.

## 8. Visual enhancement backlog

Recommended enhancements for the shared library: - Resizable and
dockable panels. - Optional glass-like surfaces and layered depth. -
Context-sensitive glow and active-state illumination. - Animated graph
connections and node focus. - Smooth chart transitions. - Skeleton
loading and progressive data rendering. - Command palette and keyboard
shortcuts. - Drag-and-drop workspace composition. - Expandable detail
views and contextual inspectors. - Light/dark theme support, while
retaining the dark Ascension default. - Reduced-motion mode and
accessibility controls. - Consistent empty, loading, success, warning
and error states.

## 9. Verification gaps

The following require source-level inspection before being labelled
implemented: - Complete list of GPT applications and their actual
registered UI extensions. - Actual code and dependency versions for each
app. - Whether the proposed Genesis Forge, Questmaster and Warden panels
exist in working interfaces. - Exact component properties, events and
data contracts. - Which components are duplicated across applications
and which are unique. - Current deployment and runtime status.

**Registry principle:** this document is the portable integration
specification. It should be updated from actual source repositories and
app exports as they are inspected; it must not convert proposed UI into
falsely reported implementation history.


## 2.2 Expanded reusable interface families

The following contracts are defined in `02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md`:

- **Application shell and navigation:** `PageHeader`, `NavigationRail`, `NotificationCenter`, `CommandPalette`.
- **Dashboards and metrics:** `DashboardFrame`, `KPIGrid`, `MetricCard`, `PriorityQueue`, `StatusBadge`, `ProgressCard`.
- **Analytics:** `ChartPanel`, `ComparisonCard`, `SegmentBreakdown`, `DataQualityCard`, `FilterBar`.
- **Projects and operations:** `ProjectHeader`, `MilestoneList`, `ResourceCard`, `DocumentList`, `AgentRoster`, `AgentAssignmentPanel`, `ActivityFeed`.
- **Creative studio:** `EditorShell`, `MainCanvas`, `AudioVisualizer`, `Timeline`, `PropertiesPanel`, `TransportControls`.
- **Feedback and system states:** `Toast`, `EmptyState`, `ReadOnlyBanner`.

See `LAYOUT_REGISTRY.md` for reusable application compositions:
Command Centre, Analytics Overview, Project Workspace, Creative Editor, Data Workbench, Document Dashboard, Bento Dashboard, Split Workspace and Mobile Stack.

See `MOUNT_INSTRUCT.md` for cross-account import and resume behaviour, and `09_IMPLEMENTATION/CHATGPT_VISUAL_ADAPTER.md` for the ChatGPT rendering strategy.

**Portability note:** the registry and specifications can be imported into another ChatGPT account. They do not automatically install executable components, transfer memory, grant connector permissions or provide an external runtime.


## 8. Integrated UI extension architecture

See `UI_EXTENSION_ARCHITECTURE.md` for the portable three-layer architecture, logical import packages, full A–F reusable component catalogue and Neon Dark visual treatment.

The architecture is organised as:
- UI Extension Registry: inventory and provenance across existing GPT applications.
- Universal UI Component Library: reusable component, layout, widget and interaction contracts.
- Visual Enhancement System: reusable design tokens, themes, animation, lighting, depth and responsive treatments.

The import boundaries are `ui-core`, `ui-components`, `ui-visualisations`, `ui-workflows`, `ui-resources`, `ui-interactions` and `ui-themes`. These are logical package boundaries; they do not assert that separately published executable packages already exist.

### Additional catalogue coverage

The registry taxonomy also explicitly includes:
- Navigation/application structure: dynamic headers, collapsible groups, multi-tab workspaces, project and agent switchers, command palettes, contextual menus, notification feeds, synchronisation indicators, modals and drawers.
- Dashboards/information: KPI and metric cards, progress indicators, activity timelines, searchable lists, filters, expandable panels, comparison panels and system-health indicators.
- Visualisations: circular relationship diagrams, behavioural feedback loops, probability distributions, trajectory projections, heatmaps, time-series, waveform/audio-spectrum and hierarchy displays.
- Agent/automation: role assignment, trigger configuration, queues, execution logs, communication streams, approvals, retry/error panels, batch controls and weekly manifests.
- Resources/knowledge: file explorer, resource registry, metadata editor, version history, provenance, previews, import/export, dependency visualisation, knowledge graph, search/retrieval and validation.
- Interactive applications: simulation/scenario controls, questionnaires, reflection journals, achievements, quests, challenges, audio players, waveform controls, interactive maps/nodes and real-time output panels.

All entries remain subject to the evidence/status rules above. A catalogue entry is not implementation verification.
```


---

## SOURCE FILE: `00_PORTAL/PORTAL.md`

```markdown
---
author: "Luke Nallen"
---
```


---

## SOURCE FILE: `01_DESIGN_SYSTEM/INSTRUCT.md`

```markdown
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
```


---

## SOURCE FILE: `01_DESIGN_SYSTEM/starter_tokens.css`

```css
:root {
  color-scheme: dark;
  --canvas: #0b0d12;
  --surface-1: #11151d;
  --surface-2: #171d28;
  --surface-raised: #202938;
  --text-primary: #f4f6fb;
  --text-secondary: #b4bdcc;
  --text-muted: #8792a5;
  --border-subtle: rgba(190, 205, 230, 0.12);
  --border-strong: rgba(190, 205, 230, 0.24);
  --accent-primary: #8b7cff;
  --accent-secondary: #42d6e8;
  --success: #35b889;
  --warning: #e8ad4d;
  --danger: #ed6575;
  --radius-control: 10px;
  --radius-card: 16px;
  --radius-feature: 22px;
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-6: 24px;
  --space-8: 32px;
  --shadow-panel: 0 12px 36px rgba(0, 0, 0, 0.22);
}
[data-theme="light"] {
  color-scheme: light;
  --canvas: #f5f7fb;
  --surface-1: #ffffff;
  --surface-2: #eef2f8;
  --surface-raised: #ffffff;
  --text-primary: #172033;
  --text-secondary: #4d5a70;
  --text-muted: #69778d;
  --border-subtle: rgba(24, 40, 68, 0.10);
  --border-strong: rgba(24, 40, 68, 0.20);
  --shadow-panel: 0 12px 36px rgba(25, 42, 70, 0.09);
}
```


---

## SOURCE FILE: `01_DESIGN_SYSTEM/THEME_PRESETS/INSTRUCT.md`

```markdown
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
```


---

## SOURCE FILE: `01_DESIGN_SYSTEM/THEME_PRESETS/THEME_REGISTRY.md`

```markdown
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
```


---

## SOURCE FILE: `01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`

```json
{
  "version": "1.0.0",
  "principle": "Presets are reusable starting points; app branding is applied as a small override layer.",
  "presets": {
    "neutral-product": {
      "label": "Neutral Product",
      "description": "Balanced default for general-purpose SaaS and productivity tools.",
      "tokens": {
        "canvas": "#0B0D12",
        "surface-1": "#121722",
        "surface-2": "#1A2230",
        "surface-raised": "#222D3D",
        "text-primary": "#F4F6FA",
        "text-secondary": "#B8C2D2",
        "text-muted": "#8793A5",
        "accent-primary": "#7186FF",
        "accent-secondary": "#49BBD0",
        "border-subtle": "rgba(190,205,230,.12)"
      }
    },
    "light-product": {
      "label": "Light Product",
      "description": "Bright, clean workspace for productivity and content-heavy applications.",
      "tokens": {
        "canvas": "#F5F7FB",
        "surface-1": "#FFFFFF",
        "surface-2": "#EEF2F8",
        "surface-raised": "#FFFFFF",
        "text-primary": "#172033",
        "text-secondary": "#4D5A70",
        "text-muted": "#69778D",
        "accent-primary": "#4D5CE6",
        "accent-secondary": "#087E91",
        "border-subtle": "rgba(24,40,68,.12)"
      }
    },
    "high-contrast": {
      "label": "High Contrast",
      "description": "Maximum legibility for accessibility-focused or dense operational interfaces.",
      "tokens": {
        "canvas": "#000000",
        "surface-1": "#101010",
        "surface-2": "#1D1D1D",
        "surface-raised": "#292929",
        "text-primary": "#FFFFFF",
        "text-secondary": "#E5E5E5",
        "text-muted": "#C8C8C8",
        "accent-primary": "#FFE45C",
        "accent-secondary": "#64E8FF",
        "border-subtle": "rgba(255,255,255,.35)"
      }
    },
    "creative-studio": {
      "label": "Creative Studio",
      "description": "Expressive but controlled palette for creator, media and design tools.",
      "tokens": {
        "canvas": "#111019",
        "surface-1": "#191725",
        "surface-2": "#242039",
        "surface-raised": "#30294A",
        "text-primary": "#F7F4FF",
        "text-secondary": "#C9C1DE",
        "text-muted": "#9A91B4",
        "accent-primary": "#B38AFF",
        "accent-secondary": "#F08BBE",
        "border-subtle": "rgba(210,190,255,.16)"
      }
    },
    "data-workbench": {
      "label": "Data Workbench",
      "description": "Low-distraction analytical theme with clear chart and status semantics.",
      "tokens": {
        "canvas": "#0D1318",
        "surface-1": "#141E25",
        "surface-2": "#1B2932",
        "surface-raised": "#253640",
        "text-primary": "#F0F6F8",
        "text-secondary": "#B5C7CF",
        "text-muted": "#8298A3",
        "accent-primary": "#58B9D8",
        "accent-secondary": "#8BCB9A",
        "border-subtle": "rgba(185,215,225,.14)"
      }
    },
    "warm-editorial": {
      "label": "Warm Editorial",
      "description": "Editorial and reading-oriented theme with warm surfaces and restrained accents.",
      "tokens": {
        "canvas": "#F4F0E8",
        "surface-1": "#FFFCF5",
        "surface-2": "#EAE4D8",
        "surface-raised": "#FFFFFF",
        "text-primary": "#28251F",
        "text-secondary": "#5D574D",
        "text-muted": "#777064",
        "accent-primary": "#9A5B3D",
        "accent-secondary": "#58786C",
        "border-subtle": "rgba(55,45,30,.14)"
      }
    },
    "neon-dark": {
      "label": "Neon Dark",
      "description": "Optional high-energy dark interface treatment using violet and cyan lighting accents, layered surfaces and restrained neon detail. Use selectively; preserve contrast and reduced-motion support.",
      "tokens": {
        "canvas": "#050509",
        "surface-1": "#101018",
        "surface-2": "#191927",
        "surface-raised": "#242437",
        "text-primary": "#F7F7FC",
        "text-secondary": "#C4C4D6",
        "text-muted": "#9292AA",
        "accent-primary": "#A855F7",
        "accent-secondary": "#22D3EE",
        "border-subtle": "rgba(168,85,247,.22)",
        "border-strong": "rgba(34,211,238,.42)",
        "focus-ring": "#22D3EE",
        "success": "#34D399",
        "warning": "#FBBF24",
        "danger": "#FB7185",
        "info": "#38BDF8"
      }
    }
  }
}
```


---

## SOURCE FILE: `02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md`

```markdown
---
title: Expanded Universal Component Contracts
version: 1.0.0
updated: 2026-11-23
status: documented-component-specifications
author: "Luke Nallen"
---

# Expanded Universal Component Contracts

This catalogue extends the existing component registry with the reusable patterns represented in the supplied Operations, Analytics, Project Workspace, Creative Studio and theme reference images. These are specifications, not claims that executable implementations already exist.

## 1. Application frame and navigation

### `AppShell`
Purpose: shared outer application frame.
Props: `brand`, `title`, `status`, `navigation`, `activeRoute`, `userActions`, `sidebarMode`.
Slots: `topbar`, `sidebar`, `main`, `rightPanel`, `footer`.
Events: `onNavigate(route)`, `onToggleSidebar()`.
States: loading, ready, offline.
Responsive: persistent sidebar on wide screens; drawer or bottom navigation on narrow screens.

### `PageHeader`
Props: `title`, `eyebrow`, `subtitle`, `status`, `actions`, `breadcrumbs`.
Events: action callbacks supplied by host.
Rules: title and status must remain readable at mobile widths.

### `NavigationRail`
Props: `items`, `activeId`, `collapsed`, `orientation`.
Events: `onSelect(id)`, `onCollapseChange(value)`.
Accessibility: semantic navigation landmark; accessible labels for icon-only items.

### `NotificationCenter`
Props: `items`, `unreadCount`, `emptyMessage`.
Events: `onOpen(itemId)`, `onMarkRead(itemId)`, `onMarkAllRead()`.
Security: notifications are source data; do not expose private details beyond the host's permissions.

## 2. Dashboard and metrics

### `DashboardFrame`
Props: `title`, `description`, `periodLabel`, `status`, `maxWidth`, `density`.
Slots: `header`, `filters`, `primary`, `secondary`, `footer`.
Responsive: fluid width, consistent page gutters, grid collapse.

### `KPIGrid`
Props: `items`, `columns`, `density`, `comparisonMode`.
Each item: `{ id, label, value, unit?, delta?, deltaLabel?, trend?, status?, source? }`.
Rules: preserve units; delta must identify its comparison baseline; omit unsupported values.

### `MetricCard`
Props: `label`, `value`, `unit`, `delta`, `deltaDirection`, `comparisonLabel`, `icon`, `description`, `status`.
States: loading skeleton, unavailable, normal.
Accessibility: announce label, value and comparison together.

### `PriorityQueue`
Props: `items`, `sort`, `showOwner`, `showDueDate`.
Item: `{ id, title, category?, priority, status, owner?, dueAt?, href? }`.
Events: `onOpen(id)`, optional `onStatusChange(id, status)`.
Rules: distinguish priority from execution status.

### `StatusBadge`
Props: `label`, `tone`, `icon`, `size`.
Tones: neutral, info, success, warning, danger.
Rules: never rely on colour alone.

### `ProgressCard`
Props: `title`, `value`, `max`, `percentage?`, `supportingText`, `status`, `milestones?`.
Rules: percentage must be derived from supplied values or explicitly sourced.

## 3. Analytics and data visualisation

### `ChartPanel`
Props: `title`, `subtitle`, `series`, `xKey`, `yFormat`, `legend`, `annotation`, `dataDisclosure`.
Slots: `chart`, `legend`, `footer`.
States: loading, empty, error, ready.
Rules: chart data must be source-backed or prominently labelled illustrative.

### `ComparisonCard`
Props: `label`, `currentValue`, `previousValue`, `delta`, `periodLabel`, `format`.
Rules: comparison periods must be explicit and comparable.

### `SegmentBreakdown`
Props: `title`, `segments`, `visualisation` (`bar` | `donut` | `list`).
Segment: `{ id, label, value, share?, colourToken? }`.
Rules: shares must sum/round transparently; use labels in addition to colour.

### `DataQualityCard`
Props: `status`, `lastRefreshed`, `checks`, `issues`, `sourceLabel`.
Statuses: validated, warning, failed, unknown.
Rules: only show "validated" when actual checks support it; never invent refresh times.

### `FilterBar`
Props: `filters`, `activeValues`, `presets`, `compareEnabled`.
Events: `onChange(values)`, `onReset()`, `onCompare()`.
Responsive: horizontal chips may wrap; provide accessible overflow handling.

## 4. Project and work management

### `ProjectHeader`
Props: `projectName`, `workspaceLabel`, `status`, `description`, `actions`, `owner`.
Composition: `PageHeader` plus project metadata.

### `MilestoneList`
Props: `items`, `showDates`, `showOwners`, `groupBy`.
Item: `{ id, title, status, dueAt?, owner?, description? }`.
Statuses: complete, in-progress, upcoming, blocked, cancelled.
Events: `onOpen(id)`, optional `onStatusChange`.

### `ResourceCard`
Props: `kind`, `title`, `count`, `supportingText`, `icon`, `href`.
Use for tasks, documents, datasets, assets and other resource classes.

### `DocumentList`
Props: `items`, `sort`, `groupBy`, `showUpdatedAt`.
Item: `{ id, title, type?, updatedAt?, status?, href? }`.
Events: `onOpen(id)`, optional `onDownload(id)`.

### `AgentRoster`
Props: `agents`, `view` (`grid` | `list`), `showCapabilities`.
Agent: `{ id, name, role, status, runtime?, currentTask?, lastActive? }`.
Rules: distinguish assigned role, configured runtime and proven live activity.

### `AgentAssignmentPanel`
Props: `assignees`, `availableAgents`, `assignmentTarget`, `permissions`.
Events: `onAssign(agentId, targetId)`, `onUnassign(agentId, targetId)`.
Rules: assignment is a real mutation; require host permission and confirmation where appropriate.

## 5. Creative studio and editor

### `EditorShell`
Props: `title`, `saveState`, `toolItems`, `activeTool`, `layout`.
Slots: `toolRail`, `canvas`, `inspector`, `timeline`, `footer`.
States: saved, saving, unsaved, error.
Rules: do not display "Saved" without confirmation from the host.

### `MainCanvas`
Props: `content`, `zoom`, `selection`, `background`, `readOnly`.
Events: `onSelectionChange`, `onContentChange` only when editing is supported.
Rules: display-only hosts must not imply editing.

### `AudioVisualizer`
Props: `samples`, `duration`, `playhead`, `tracks`, `displayMode` (`waveform` | `spectrum` | `envelope`).
Events: `onSeek(time)` where supported.
Rules: visual representation does not imply audio playback or signal analysis; label synthetic/demo data.

### `Timeline`
Props: `tracks`, `duration`, `playhead`, `scale`, `snap`.
Events: `onSeek(time)`, `onSelectClip(id)`, optional edit events.
Responsive: allow horizontal scroll within the timeline region, not the whole page.

### `PropertiesPanel`
Props: `sections`, `selectedItem`, `readOnly`.
Events: `onPropertyChange(path, value)` only when editing is enabled.
Rules: show units and validation constraints for editable properties.

### `TransportControls`
Props: `isPlaying`, `position`, `duration`, `canPlay`, `canRecord`.
Events: `onPlay`, `onPause`, `onStop`, `onSeek`.
Rules: hide unsupported controls; never imply playback if no media runtime exists.

## 6. System and interaction components

### `CommandPalette`
Props: `commands`, `recentItems`, `placeholder`, `shortcutHint`.
Events: `onExecute(commandId)`, `onSearch(query)`.
Rules: only expose commands the host can actually execute.

### `Toast`
Props: `message`, `tone`, `duration`, `action`.
Rules: persistent errors require a durable alert, not a transient toast.

### `EmptyState`
Props: `title`, `description`, `illustration?`, `primaryAction?`, `secondaryAction?`.
Rules: actions must have real destinations or callbacks.

### `ReadOnlyBanner`
Props: `message`, `sourceLabel`.
Rules: use whenever a visual preview cannot mutate its source.

### `ActivityFeed`
Props: `items`, `groupByDate`, `showActor`, `showTimestamp`.
Item: `{ id, summary, actor?, category?, occurredAt?, source? }`.
Rules: never fabricate actor, timestamp or event provenance.

## Composition examples

### Operations command centre
`AppShell > DashboardFrame > KPIGrid + PriorityQueue + AgentRoster + ActivityFeed`

### Performance analytics
`DashboardFrame > FilterBar + KPIGrid + ChartPanel + SegmentBreakdown + DataQualityCard`

### Project workspace
`AppShell > ProjectHeader + ProgressCard + ResourceCardGrid + MilestoneList + ActivityFeed`

### Creative editor
`EditorShell > NavigationRail + MainCanvas + AudioVisualizer + PropertiesPanel`

## Status

All contracts in this document are `DOCUMENTED`. Promote to `IMPLEMENTATION-VERIFIED` only after an implementation is inspected and its behaviour is tested in a target runtime.


## 7. Extended catalogue and architecture reference

The complete reusable catalogue taxonomy, including navigation, dashboard, visualisation, agent/automation, resource/knowledge and interactive-application components, is maintained in `../UI_EXTENSION_ARCHITECTURE.md`.

The catalogue taxonomy is broader than the set of components with detailed contracts in this file. Items without a contract here remain documented catalogue entries, not implementation-verified components. Add a detailed contract before treating a new item as ready for implementation.
```


---

## SOURCE FILE: `02_COMPONENT_LIBRARY/INSTRUCT.md`

```markdown
---
title: Component Library
type: ui-standard
updated: 2026-11-23
author: "Luke Nallen"
---

# Component Library

## Component contract
Every reusable component documents: purpose, anatomy, variants, props, events, controlled/uncontrolled state, loading and error behaviour, keyboard support, responsive rules, theme tokens, examples and tests.

## Core component families
### App shell and navigation
`AppShell`, `TopBar`, `Sidebar`, `MobileNav`, `Breadcrumbs`, `WorkspaceSwitcher`, `Tabs`, `CommandPalette`, `ContextMenu`, `NotificationCenter`, `Search`.

### Actions and forms
`Button`, `IconButton`, `ButtonGroup`, `TextInput`, `Textarea`, `Select`, `Combobox`, `Checkbox`, `RadioGroup`, `Switch`, `Slider`, `DatePicker`, `FormField`, `ValidationMessage`.

### Content and feedback
`Card`, `Panel`, `Accordion`, `Tooltip`, `Popover`, `Modal`, `Drawer`, `Toast`, `Alert`, `Badge`, `Avatar`, `Skeleton`, `EmptyState`, `ErrorState`, `Progress`.

### Data and operations
`DataTable`, `FilterBar`, `MetricCard`, `StatusBadge`, `Timeline`, `ActivityFeed`, `TreeView`, `FileList`, `LogViewer`, `DiffViewer`, `Pagination`.

### Visualisation
`LineChart`, `BarChart`, `AreaChart`, `Heatmap`, `NetworkGraph`, `NodeGraph`, `StateTransition`, `FeedbackLoop`, `ResonanceGauge`, `Waveform`, `AudioSpectrum`, `HierarchyTree`.

### Document rendering
`MarkdownDocumentRenderer` and `MarkdownDashboardRenderer` provide a host-adapter pattern for rendering canonical Markdown documents as navigable views. Prefer the host-native parser and link resolver; preserve callouts, tables, disclosures and source context. Read-only mode must omit write APIs, not merely hide edit controls. See `09_IMPLEMENTATION/markdown_dashboard_renderer.md` for the complete contract.

### Agents and workflows
`AgentCard`, `AgentStatus`, `RoleAssignment`, `TriggerEditor`, `TaskQueue`, `TaskManifest`, `ExecutionLog`, `WorkflowCanvas`, `ApprovalPanel`, `RetryPanel`, `BatchRunControls`, `WeeklyReport`.

## Component quality rules
- Prefer composition and slots over giant components with dozens of unrelated boolean props.
- Use explicit variants such as `primary`, `secondary`, `quiet`, `danger`; do not create visually ambiguous controls.
- Destructive actions require clear labels and confirmation proportional to impact.
- Icon-only controls require accessible names and visible tooltips where appropriate.
- Inputs need labels, descriptions, validation and error association.
- Tables need sorting/filtering semantics, empty states and a mobile strategy.
- Charts need titles, units, legends, accessible summaries and a non-visual data alternative.
- Never make a whole card clickable if it contains multiple independent actions.

## State matrix
For each interactive component specify: idle, hover, focus-visible, pressed, selected, disabled, loading, success, warning and error where relevant. State must be visually distinguishable and programmatically exposed.

## Reuse and extension
Search the registry before creating a new component. If a product needs a special case, extend the base component through a documented variant or wrapper. Keep domain-specific logic outside the shared primitive.

## Style components are separate from functional components
Visual treatments such as `GlassSurface`, `BentoGrid`, `MetricTile`, `PageHeader`, `SidebarShell` and `WorkspaceSplit` are catalogued in `STYLE_COMPONENTS/INSTRUCT.md`. They must consume semantic tokens and must not contain product-specific branding. See the CSS starter implementation in that folder.
```


---

## SOURCE FILE: `02_COMPONENT_LIBRARY/component_registry.json`

```json
{
  "version": "2.5.0",
  "updated": "2026-11-28",
  "status": "integrated-portable-ui-extension-architecture",
  "component_families": {
    "navigation": [
      "AppShell",
      "TopBar",
      "Sidebar",
      "MobileNav",
      "Breadcrumbs",
      "WorkspaceSwitcher",
      "Tabs",
      "CommandPalette",
      "ContextMenu",
      "NotificationCenter",
      "Search"
    ],
    "actions_forms": [
      "Button",
      "IconButton",
      "ButtonGroup",
      "TextInput",
      "Textarea",
      "Select",
      "Combobox",
      "Checkbox",
      "RadioGroup",
      "Switch",
      "Slider",
      "DatePicker",
      "FormField",
      "ValidationMessage"
    ],
    "content_feedback": [
      "Card",
      "Panel",
      "Accordion",
      "Tooltip",
      "Popover",
      "Modal",
      "Drawer",
      "Toast",
      "Alert",
      "Badge",
      "Avatar",
      "Skeleton",
      "EmptyState",
      "ErrorState",
      "Progress"
    ],
    "data_operations": [
      "DataTable",
      "FilterBar",
      "MetricCard",
      "StatusBadge",
      "Timeline",
      "ActivityFeed",
      "TreeView",
      "FileList",
      "LogViewer",
      "DiffViewer",
      "Pagination"
    ],
    "visualisation": [
      "LineChart",
      "BarChart",
      "AreaChart",
      "Heatmap",
      "NetworkGraph",
      "NodeGraph",
      "StateTransition",
      "FeedbackLoop",
      "ResonanceGauge",
      "Waveform",
      "AudioSpectrum",
      "HierarchyTree"
    ],
    "agents_workflows": [
      "AgentCard",
      "AgentStatus",
      "RoleAssignment",
      "TriggerEditor",
      "TaskQueue",
      "TaskManifest",
      "ExecutionLog",
      "WorkflowCanvas",
      "ApprovalPanel",
      "RetryPanel",
      "BatchRunControls",
      "WeeklyReport"
    ],
    "document_rendering": [
      "MarkdownDocumentRenderer",
      "MarkdownDashboardRenderer"
    ],
    "application_shell": [
      "PageHeader",
      "NavigationRail",
      "NotificationCenter",
      "CommandPalette"
    ],
    "dashboard": [
      "DashboardFrame",
      "KPIGrid",
      "PriorityQueue",
      "ProgressCard",
      "ComparisonCard",
      "DataQualityCard",
      "SegmentBreakdown",
      "ChartPanel"
    ],
    "project_workspace": [
      "ProjectHeader",
      "MilestoneList",
      "ResourceCard",
      "DocumentList",
      "AgentRoster",
      "AgentAssignmentPanel"
    ],
    "creative_studio": [
      "EditorShell",
      "MainCanvas",
      "AudioVisualizer",
      "Timeline",
      "PropertiesPanel",
      "TransportControls"
    ],
    "interaction_feedback": [
      "Toast",
      "EmptyState",
      "ReadOnlyBanner",
      "ActivityFeed"
    ],
    "navigation_application_structure": [
      "DynamicApplicationHeader",
      "SidebarNavigation",
      "CollapsibleNavigationGroup",
      "MultiTabWorkspace",
      "BreadcrumbNavigation",
      "ProjectSwitcher",
      "AgentSwitcher",
      "ContextualActionMenu",
      "VersionIndicator",
      "SynchronisationIndicator",
      "Modal",
      "Drawer"
    ],
    "dashboard_information": [
      "ActivityTimeline",
      "SearchableResourceList",
      "SortingControl",
      "ExpandableInformationPanel",
      "DashboardGrid",
      "ComparisonPanel",
      "SystemHealthIndicator",
      "CircularProgress"
    ],
    "visualisation_extended": [
      "CircularRelationshipDiagram",
      "BehaviouralFeedbackLoop",
      "ProbabilityDistribution",
      "TrajectoryProjection",
      "TimeSeriesChart",
      "WaveformDisplay",
      "HierarchicalTreeDiagram"
    ],
    "agent_automation_extended": [
      "AgentProfileCard",
      "RoleAssignmentPanel",
      "TriggerConfiguration",
      "AgentCommunicationStream",
      "ErrorPanel",
      "BatchExecutionControls",
      "WeeklyTaskManifest"
    ],
    "resource_knowledge": [
      "FileExplorer",
      "ResourceRegistry",
      "MetadataEditor",
      "VersionHistory",
      "ProvenanceViewer",
      "DocumentPreview",
      "ImportExportControls",
      "DependencyVisualiser",
      "KnowledgeGraph",
      "SearchRetrievalInterface",
      "ResourceValidationPanel"
    ],
    "interactive_application": [
      "SimulationControls",
      "ScenarioConfiguration",
      "InteractiveQuestionnaire",
      "ReflectionJournal",
      "AchievementSystem",
      "QuestInterface",
      "ChallengeCard",
      "AudioPlayer",
      "WaveformControls",
      "InteractiveMap",
      "InteractiveNode",
      "RealTimeOutputPanel"
    ],
    "research_evidence": [
      "EvidenceLedger",
      "SourceCard",
      "ClaimCard",
      "ResearchStageBoard",
      "ReleaseChecklist"
    ],
    "graph_scenario": [
      "NodeInspector",
      "NetworkCanvas",
      "ScenarioWorkbench",
      "BeforeAfterCompare",
      "TrajectoryProjection"
    ],
    "workflow_execution": [
      "ExecutionTimeline",
      "ApprovalGate",
      "RetryResumePanel",
      "DependencyGraph",
      "ChainOfCommandView"
    ],
    "library_management": [
      "LibraryImporter",
      "ComponentPicker",
      "ThemePicker",
      "DesignTokenInspector",
      "DependencyReport",
      "CompatibilityMatrix"
    ],
    "publishing_editorial": [
      "ChapterNavigator",
      "EditorialIssueList",
      "ProofreadingChecklist",
      "RevisionHistory",
      "ManuscriptPreview"
    ],
    "commerce_operations": [
      "OrderQueue",
      "InventoryPanel",
      "LocationComparison",
      "FulfilmentBoard",
      "ExceptionQueue"
    ],
    "provenance_governance": [
      "EvidenceLedger",
      "ProvenanceViewer",
      "AuditTrail",
      "PermissionBoundary",
      "DataDisclosure"
    ]
  },
  "theme_families": [
    "neutral-product",
    "light-product",
    "high-contrast",
    "creative-studio",
    "data-workbench",
    "warm-editorial",
    "neon-dark"
  ],
  "evidence_labels": [
    "SOURCE-VERIFIED",
    "DOCUMENTED",
    "INFERRED",
    "PROPOSED",
    "NOT INSPECTED"
  ],
  "app_inventory": "03_APP_LIBRARY/APP_INVENTORY.json",
  "theme_architecture": {
    "presets": "../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json",
    "style_components": "STYLE_COMPONENTS/",
    "rule": "Theme presets and visual treatments are app-agnostic; app profiles supply only brand overrides."
  },
  "style_components": [
    "Callout",
    "DashboardFrame",
    "NavigationLink",
    "ReadOnlyBanner"
  ],
  "component_contracts": {
    "MarkdownDocumentRenderer": "09_IMPLEMENTATION/markdown_dashboard_renderer.md",
    "MarkdownDashboardRenderer": "09_IMPLEMENTATION/markdown_dashboard_renderer.md",
    "PageHeader": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "NavigationRail": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "NotificationCenter": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "CommandPalette": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "DashboardFrame": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "KPIGrid": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "PriorityQueue": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "ProgressCard": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "ComparisonCard": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "DataQualityCard": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "SegmentBreakdown": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "ChartPanel": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "ProjectHeader": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "MilestoneList": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "ResourceCard": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "DocumentList": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "AgentRoster": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "AgentAssignmentPanel": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "EditorShell": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "MainCanvas": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "AudioVisualizer": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "Timeline": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "PropertiesPanel": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "TransportControls": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "Toast": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "EmptyState": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "ReadOnlyBanner": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "ActivityFeed": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
    "ChatGPTVisualAdapter": "09_IMPLEMENTATION/CHATGPT_VISUAL_ADAPTER.md",
    "UIExtensionArchitecture": "UI_EXTENSION_ARCHITECTURE.md"
  },
  "layout_registry": "LAYOUT_REGISTRY.md",
  "mount_instructions": "MOUNT_INSTRUCT.md",
  "app_builder_instructions": "APP_BUILDER_INSTRUCT.md",
  "portable_specification": "02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md",
  "architecture": {
    "specification": "UI_EXTENSION_ARCHITECTURE.md",
    "layers": [
      "ui-extension-registry",
      "universal-ui-component-library",
      "visual-enhancement-system"
    ],
    "logical_import_packages": {
      "ui-core": "01_DESIGN_SYSTEM/",
      "ui-components": "02_COMPONENT_LIBRARY/",
      "ui-visualisations": "02_COMPONENT_LIBRARY/ and UNIVERSAL_COMPONENT_REGISTRY.md",
      "ui-workflows": "02_COMPONENT_LIBRARY/ and 12_APP_PROFILES/",
      "ui-resources": "02_COMPONENT_LIBRARY/ and 03_APP_LIBRARY/",
      "ui-interactions": "05_INTERACTION_DESIGN/ and 02_COMPONENT_LIBRARY/",
      "ui-themes": "01_DESIGN_SYSTEM/THEME_PRESETS/ and 07_VISUAL_DESIGN/"
    },
    "package_status": "logical-import-boundaries; not claims of separately published executable packages"
  }
}
```


---

## SOURCE FILE: `02_COMPONENT_LIBRARY/STYLE_COMPONENTS/INSTRUCT.md`

```markdown
---
author: "Luke Nallen"
---

# Reusable Style Components — AI Instructions

## Purpose
Turn visual treatments into composable, reusable style components. Components must be independent of any one app's brand, domain or information architecture.

## Component catalogue

| Component | Purpose | Configurable properties |
|---|---|---|
| `Surface` | Base content surface | tone, elevation, radius, border |
| `GlassSurface` | Translucent layered surface | opacity, blur, tint, border, fallback |
| `GradientSurface` | Restrained gradient emphasis | start/end tokens, direction, intensity |
| `GlowAccent` | Focus or selected-state emphasis | colour token, blur, spread, intensity |
| `BentoGrid` | Unequal-priority modular layout | columns, gap, item span, responsive rules |
| `MetricTile` | Compact KPI presentation | label, value, unit, trend, status, density |
| `SectionHeader` | Consistent section hierarchy | title, description, actions, eyebrow |
| `PageHeader` | Page identity and primary action | title, breadcrumb, context, actions |
| `SidebarShell` | Responsive application navigation | width, collapsed state, groups, breakpoint |
| `WorkspaceSplit` | Main workspace plus inspector | ratio, min widths, dock/collapse behaviour |
| `EmptyState` | Helpful no-content state | icon, title, description, action |
| `SkeletonBlock` | Layout-preserving loading placeholder | shape, dimensions, animation mode |
| `StatusPill` | Compact semantic status | status token, label, icon |
| `ChartFrame` | Consistent chart container | title, subtitle, legend, source, actions |
| `FloatingToolbar` | Contextual tools near work surface | placement, density, keyboard behaviour |
| `DashboardFrame` | Constrains and spaces a document-led dashboard | max width, density, page padding, section gap |
| `Callout` | Semantic highlighted content block | tone, title, icon, collapsible, border placement |
| `NavigationLink` | Clear, keyboard-accessible destination link | current state, description, icon, density |
| `ReadOnlyBanner` | Persistent disclosure that a view cannot mutate source data | tone, message, optional provenance text |

## Styling contract
- Style components consume semantic tokens and expose documented variants.
- Components do not define their own product-specific brand palette.
- Effects must be configurable and have safe defaults.
- Avoid global element selectors that leak styles into host applications.
- Prefer CSS variables and component-scoped classes.
- Provide `data-theme` and `data-variant` hooks where useful.
- Every style component must have responsive, focus, disabled and reduced-motion behaviour where applicable.

## Document-led dashboard primitives

`DashboardFrame`, `Callout`, `NavigationLink` and `ReadOnlyBanner` are framework-neutral visual primitives. They complement (rather than replace) the functional `Alert`, `Accordion`, `DataTable`, `MetricCard` and navigation components in the component registry.

- `DashboardFrame` provides a readable content measure, consistent page padding and vertical rhythm. It must preserve source reading order.
- `Callout` uses semantic intent (`info`, `success`, `warning`, `critical`, `neutral`) and must not communicate meaning by colour alone. A host-native Markdown callout may be used as the rendering adapter.
- `NavigationLink` remains a real link with a destination, accessible name, visible focus and current-location semantics. Do not replace links with inert styled containers.
- `ReadOnlyBanner` is a persistent disclosure, not an authorization mechanism. The underlying renderer must independently omit write operations.

These primitives are suitable for document dashboards, knowledge workspaces and operational reporting interfaces without requiring app-specific business logic.

## Glass treatment
Use glass as a surface variant, not a separate app identity. Recommended use: floating navigation, overlays, contextual toolbars and selected feature panels. Avoid glass on every card or behind dense text. Include an opaque fallback.

## Bento layout
Use grid spans to express information priority. Ensure reading order remains logical when the grid collapses. Avoid masonry-like visual order that differs from keyboard and screen-reader order.

## Example API (framework-neutral)
```ts
type SurfaceProps = {
  tone?: "default" | "subtle" | "raised";
  elevation?: "none" | "low" | "medium" | "high";
  radius?: "sm" | "md" | "lg" | "xl";
  border?: "none" | "subtle" | "strong";
};

type GlassSurfaceProps = SurfaceProps & {
  blur?: "sm" | "md" | "lg";
  opacity?: number;
  fallback?: "surface-1" | "surface-2";
};

type BentoGridProps = {
  columns?: number;
  gap?: "sm" | "md" | "lg";
  responsive?: "stack" | "auto-fit";
};
```

## Acceptance
A style component is reusable only if it can be applied to at least two unrelated application contexts without code changes beyond token configuration and content.
```


---

## SOURCE FILE: `02_COMPONENT_LIBRARY/STYLE_COMPONENTS/reusable_style_components.css`

```css
:root {
  --ui-radius-sm: 8px;
  --ui-radius-md: 12px;
  --ui-radius-lg: 18px;
  --ui-radius-xl: 24px;
  --ui-shadow-low: 0 4px 14px rgba(0,0,0,.10);
  --ui-shadow-medium: 0 12px 32px rgba(0,0,0,.16);
  --ui-shadow-high: 0 22px 60px rgba(0,0,0,.22);
  --ui-glass-opacity: .72;
  --ui-glass-blur: 16px;
}
.ui-surface {
  color: var(--text-primary);
  background: var(--surface-1);
  border: 1px solid var(--border-subtle);
  border-radius: var(--ui-radius-lg);
}
.ui-surface[data-tone="subtle"] { background: var(--surface-2); }
.ui-surface[data-tone="raised"] { background: var(--surface-raised); box-shadow: var(--ui-shadow-low); }
.ui-glass-surface {
  color: var(--text-primary);
  background: color-mix(in srgb, var(--surface-raised) calc(var(--ui-glass-opacity) * 100%), transparent);
  border: 1px solid var(--border-strong);
  border-radius: var(--ui-radius-lg);
  -webkit-backdrop-filter: blur(var(--ui-glass-blur));
  backdrop-filter: blur(var(--ui-glass-blur));
}
@supports not ((backdrop-filter: blur(1px))) {
  .ui-glass-surface { background: var(--surface-raised); }
}
.ui-bento-grid {
  display: grid;
  grid-template-columns: repeat(12, minmax(0, 1fr));
  gap: var(--space-4, 16px);
}
.ui-bento-item { min-width: 0; grid-column: span 4; }
.ui-bento-item[data-span="6"] { grid-column: span 6; }
.ui-bento-item[data-span="8"] { grid-column: span 8; }
.ui-bento-item[data-span="12"] { grid-column: span 12; }
.ui-section-header { display:flex; align-items:flex-end; justify-content:space-between; gap:16px; }
.ui-status-pill { display:inline-flex; align-items:center; gap:6px; border-radius:999px; padding:4px 10px; }
.ui-focusable:focus-visible { outline: 2px solid var(--focus-ring, var(--accent-primary)); outline-offset: 3px; }
@media (max-width: 900px) {
  .ui-bento-item, .ui-bento-item[data-span="6"], .ui-bento-item[data-span="8"] { grid-column: span 6; }
}
@media (max-width: 600px) {
  .ui-bento-grid { grid-template-columns: minmax(0,1fr); }
  .ui-bento-item, .ui-bento-item[data-span] { grid-column: 1 / -1; }
}
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { scroll-behavior:auto !important; animation-duration:.01ms !important; transition-duration:.01ms !important; }
}


/* Document-led dashboard primitives: generic, token-driven and host-neutral. */
.ui-dashboard-frame {
  width: min(100%, var(--ui-dashboard-max-width, 72rem));
  margin-inline: auto;
  padding: var(--ui-dashboard-page-padding, clamp(1rem, 3vw, 2rem));
  display: flex;
  flex-direction: column;
  gap: var(--ui-dashboard-section-gap, 1.25rem);
  color: var(--text-primary);
}
.ui-callout {
  --ui-callout-accent: var(--accent-primary);
  min-width: 0;
  padding: var(--space-4, 1rem);
  color: var(--text-primary);
  background: var(--surface-1);
  border: 1px solid var(--border-subtle);
  border-inline-start: 3px solid var(--ui-callout-accent);
  border-radius: var(--ui-radius-md, 12px);
}
.ui-callout[data-tone="success"] { --ui-callout-accent: var(--status-success, #3b9b68); }
.ui-callout[data-tone="warning"] { --ui-callout-accent: var(--status-warning, #c58a2a); }
.ui-callout[data-tone="critical"] { --ui-callout-accent: var(--status-critical, #c44e4e); }
.ui-callout[data-tone="info"] { --ui-callout-accent: var(--accent-primary); }
.ui-navigation-link {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: var(--space-2, .5rem);
  min-width: 0;
  padding: var(--space-3, .75rem);
  color: var(--text-primary);
  background: var(--surface-1);
  border: 1px solid var(--border-subtle);
  border-radius: var(--ui-radius-md, 12px);
  text-decoration: none;
}
.ui-navigation-link:hover,
.ui-navigation-link[aria-current="page"] {
  border-color: var(--border-strong, var(--accent-primary));
  background: var(--surface-2);
}
.ui-navigation-link:focus-visible {
  outline: 2px solid var(--focus-ring, var(--accent-primary));
  outline-offset: 3px;
}
.ui-readonly-banner {
  display: flex;
  align-items: flex-start;
  gap: var(--space-3, .75rem);
  padding: var(--space-3, .75rem) var(--space-4, 1rem);
  color: var(--text-primary);
  background: var(--surface-2);
  border: 1px solid var(--border-subtle);
  border-radius: var(--ui-radius-md, 12px);
}
.ui-readonly-banner::before {
  content: "";
  flex: 0 0 .55rem;
  width: .55rem;
  height: .55rem;
  margin-top: .35em;
  border-radius: 50%;
  background: var(--status-info, var(--accent-primary));
}
@media (max-width: 600px) {
  .ui-dashboard-frame { padding: var(--ui-dashboard-mobile-padding, .75rem); }
  .ui-navigation-link { min-height: 2.75rem; }
}
```


---

## SOURCE FILE: `03_APP_LIBRARY/APP_INVENTORY.json`

```json
{
  "schema_version": "1.0.0",
  "purpose": "Index of generic, reusable application interface profiles.",
  "profiles": [
    {
      "id": "general-application",
      "file": "GENERAL_APPLICATION_PROFILE.md",
      "scope": "generic",
      "external_dependencies": []
    },
    {
      "id": "data-workbench",
      "file": "DATA_WORKBENCH_PROFILE.md",
      "scope": "generic",
      "external_dependencies": []
    },
    {
      "id": "creative-studio",
      "file": "CREATIVE_STUDIO_PROFILE.md",
      "scope": "generic",
      "external_dependencies": []
    },
    {
      "id": "editorial-content",
      "file": "EDITORIAL_CONTENT_PROFILE.md",
      "scope": "generic",
      "external_dependencies": []
    },
    {
      "id": "operations-workspace",
      "file": "OPERATIONS_WORKSPACE_PROFILE.md",
      "scope": "generic",
      "external_dependencies": []
    },
    {
      "id": "project-workspace",
      "file": "PROJECT_WORKSPACE_PROFILE.md",
      "scope": "generic",
      "external_dependencies": []
    },
    {
      "id": "resource-library",
      "file": "RESOURCE_LIBRARY_PROFILE.md",
      "scope": "generic",
      "external_dependencies": []
    },
    {
      "id": "commerce-experience",
      "file": "COMMERCE_EXPERIENCE_PROFILE.md",
      "scope": "generic",
      "external_dependencies": []
    }
  ]
}
```


---

## SOURCE FILE: `03_APP_LIBRARY/APP_INVENTORY.md`

```markdown
---
author: "Luke Nallen"
---

# Generic Application Profile Index

| Profile | Suitable interface |
|---|---|
| General Application | General-purpose SaaS and productivity |
| Data Workbench | Analytics and data exploration |
| Creative Studio | Creative production and editing |
| Editorial Content | Reading, writing and publishing |
| Operations Workspace | Tasks, workflows and approvals |
| Project Workspace | Projects, milestones and collaboration |
| Resource Library | Files, assets and knowledge collections |
| Commerce Experience | Catalogues and purchasing journeys |

Profiles are reusable templates, not a list of supported products or installed applications.
```


---

## SOURCE FILE: `03_APP_LIBRARY/INSTRUCT.md`

```markdown
---
author: "Luke Nallen"
---

# Application Profile Catalogue

This directory indexes generic application archetypes supplied by the UI Extension Library.

The profiles are product-neutral composition references. They do not inventory, identify, depend on, or load any external application. Select one or more profiles from `12_APP_PROFILES/` according to the interface task.

Host applications own their own product identity, data, business logic, authentication, integrations and runtime permissions. No external master system is required.
```


---

## SOURCE FILE: `04_DASHBOARD_DESIGN/INSTRUCT.md`

```markdown
---
title: Dashboard Design
type: ui-standard
updated: 2026-11-22
author: "Luke Nallen"
---

# Dashboard Design

## Dashboard purpose
A dashboard answers: what is happening, what needs attention, why, and what can I do next? It is not a collection of decorative cards.

## Recommended hierarchy
1. **Orientation:** product/workspace name, current scope, date or selected period.
2. **Primary action:** the one task users most often need to perform.
3. **Health/summary:** a small set of meaningful metrics with units and comparison context.
4. **Priority work:** blockers, exceptions, upcoming deadlines and next actions.
5. **Exploration:** charts, activity, history and secondary modules.

## Layout patterns
- Operational command centre: narrow global nav, central task/work queue, contextual inspector.
- Analytics: filter row, KPI strip, primary trend chart, breakdowns and source notes.
- Project workspace: project switcher, status summary, milestones, files and activity.
- Creator/editor: compact tool rail, large canvas/editor, properties inspector and preview.

## KPI and data integrity
- Every metric needs a definition, unit, time window, source and freshness indicator.
- Distinguish live telemetry from a recorded snapshot.
- Avoid unsupported precision, misleading truncated axes and ambiguous percentages.
- Show comparison baseline and directionality where useful.
- Use consistent status labels and never imply execution merely because a task is listed.

## Data density
Use progressive disclosure: summary first, detail on demand. Keep tables scannable with aligned numeric columns, sticky headers only when useful, filters close to the data and clear empty states.

## Widget rules
Every widget needs a title, purpose, source, loading/empty/error states, refresh semantics and a useful action or insight. Allow rearrangement only if it improves real workflows and persists predictably.



## Expanded dashboard compositions

Use `LAYOUT_REGISTRY.md` for reusable Command Centre, Analytics Overview, Project Workspace, Bento Dashboard and Document Dashboard layouts. Compose these from the expanded component contracts in `02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md`. Do not hardcode screenshot-specific values; bind metrics and statuses to actual sources or label them illustrative.
```


---

## SOURCE FILE: `05_INTERACTION_DESIGN/INSTRUCT.md`

```markdown
---
title: Interaction Design
type: ui-standard
updated: 2026-11-22
author: "Luke Nallen"
---

# Interaction Design

## Interaction principles
- Make available actions visible and their outcomes predictable.
- Give immediate feedback for local actions; show progress for longer operations.
- Prevent accidental destructive actions and preserve undo where feasible.
- Keep transitions purposeful and short; motion must explain spatial or state change.

## Motion
Use motion to show continuity, hierarchy, expansion, navigation or progress. Avoid perpetual motion, excessive parallax and animation that delays task completion. Respect `prefers-reduced-motion`; provide non-animated equivalents.

## Feedback patterns
- Inline validation for form errors.
- Toasts for transient confirmations that do not require action.
- Persistent alerts for important unresolved conditions.
- Progress indicators for known-duration work; indeterminate progress for unknown duration.
- Skeletons when layout is known; spinners only for small local waits.
- Empty states explain why no data exists and offer a relevant next step.

## State management
Separate server state, local UI state and durable user preferences. Define source of truth, loading, stale, optimistic update, rollback, retry and conflict behaviour. Avoid duplicate state copies that can drift.

## Keyboard and pointer
All primary workflows must be keyboard operable. Provide visible focus, logical tab order, Escape handling for overlays, Enter/Space activation and drag alternatives. Do not encode critical actions exclusively in hover.

## Async and agent operations
Show queued, running, waiting-for-approval, blocked, succeeded, failed and cancelled states distinctly. Include run identity, timestamps, output links and error details. Never represent an agent as running without runtime evidence.
```


---

## SOURCE FILE: `06_RESPONSIVE_DESIGN/INSTRUCT.md`

```markdown
---
title: Responsive Design
type: ui-standard
updated: 2026-11-22
author: "Luke Nallen"
---

# Responsive Design

## Design from constraints
Start with the smallest supported viewport and expand. Breakpoints should be driven by content failure, not device brand names. Test narrow phones, landscape phones, tablets, laptops and wide displays.

## Adaptive navigation
- Desktop: persistent sidebar when it supports frequent navigation.
- Tablet: collapsible rail or drawer.
- Mobile: compact top bar plus bottom navigation or navigation drawer, depending on task frequency.
- Preserve current location and back-navigation context when navigation collapses.

## Responsive data
- Reflow cards into one column.
- Convert dense tables to labelled row cards or provide intentional horizontal scrolling with clear affordance.
- Keep essential metrics and actions visible; move secondary controls into filters or overflow.
- Charts must resize labels, legends and tooltips without losing meaning.

## Touch ergonomics
Use comfortable hit targets (typically around 44px), adequate spacing and no hover-only actions. Avoid placing destructive controls next to frequent primary actions.

## Responsive testing
Check text wrapping, long filenames, large numbers, empty/error states, dialogs, virtual keyboards, sticky elements and orientation changes. Avoid fixed heights that clip content.
```


---

## SOURCE FILE: `07_VISUAL_DESIGN/INSTRUCT.md`

```markdown
---
title: Visual Design
type: ui-standard
updated: 2026-11-22
author: "Luke Nallen"
---

# Visual Design

## Composition
Create a clear focal point, establish alignment, group related information and use whitespace to make complexity understandable. Apply contrast and scale intentionally; do not make every element compete for attention.

## Aesthetic direction
Professional SaaS quality comes from consistency, proportion, typography, hierarchy, detail and restraint—not from adding more effects. Use bento grids when they clarify different module priorities. Use glassmorphism only where layering is meaningful and contrast remains strong.

## Surface and depth
Use a small surface palette, subtle separators and restrained shadows. Reserve gradients, glow and saturated accents for primary actions, active navigation, selected data or key visualisations.

## Iconography
Use one coherent icon family, consistent stroke/fill and predictable sizing. Icons supplement labels; avoid ambiguous glyphs. Preserve logos and canonical sigils without stretching, recolouring or redrawing unless brand rules explicitly allow it.

## Data visual design
Select chart types that match the question. Label axes and units, explain colour meaning, show uncertainty where applicable and avoid 3D charts or decorative distortion. Include a textual summary for important visual findings.

## Brand balance
Each app profile defines its own accent, logo use, tone and imagery. Shared design tokens preserve cohesion while product-specific visual signatures preserve recognition.
```


---

## SOURCE FILE: `07_VISUAL_DESIGN/PRACTICAL_UI_DESIGN_RECIPE.md`

```markdown
---
author: "Luke Nallen"
---

# Practical UI Design and Build Recipe

## Before writing code
- Identify the one primary user task and the top three supporting tasks.
- Sketch the page hierarchy and navigation.
- List data inputs, permissions, empty/loading/error states and responsive constraints.
- Read the relevant app profile and inspect the current implementation.

## Layout recipe
- Use a stable application shell.
- Give the page a clear title, context and primary action.
- Group related content into sections.
- Use a responsive grid with consistent gaps.
- Put the most important content first.
- Keep secondary controls close to the content they affect.
- Avoid nested cards inside cards unless grouping truly requires it.

## Attractive dashboard recipe
- Use one strong page title and a compact supporting description.
- Present 3–5 high-value summary metrics, not a wall of KPIs.
- Give the main chart or work queue enough space to be useful.
- Use a bento grid only for distinct content priorities.
- Keep chart colours semantically consistent.
- Show freshness, source and date range.
- Use concise labels and aligned numbers.
- Provide useful empty states instead of blank rectangles.

## Glassmorphism recipe
- Apply translucent surfaces selectively to overlays, floating panels or featured elements.
- Keep the underlying text contrast strong.
- Add a subtle border to define the glass edge.
- Use blur sparingly; provide a solid surface fallback.
- Do not put every card on a translucent blurred layer.

## Responsive recipe
- Collapse sidebars before they become cramped.
- Stack cards and controls in a predictable reading order.
- Convert dense tables to mobile row cards or an intentional scroll container.
- Move secondary inspectors into drawers.
- Preserve primary actions and context.

## Final polish
- Align edges and baselines.
- Remove redundant labels and decorative separators.
- Make interactive states visible.
- Use consistent icon sizes.
- Check long titles, empty content, large numbers and narrow widths.
- Verify that the interface remains understandable without colour or animation.
```


---

## SOURCE FILE: `07_VISUAL_DESIGN/REFERENCE_IMAGE_REQUIREMENTS.md`

```markdown
---
author: "Luke Nallen"
---

# Design Reference Requirements — 22 November 2026

The supplied reference images establish two mandatory library goals.

## Application coverage
Every application built within the Ecosystem Master receives its own UI profile, design guidance and reusable interface patterns. The inventory must distinguish real application code from documented workflows, prototypes, planned products and non-app knowledge workspaces.

## Design intelligence
The library must teach applications to implement:
- Professional SaaS-quality interfaces.
- Modern dark and light themes.
- Glassmorphism and restrained visual effects.
- Bento-grid layouts.
- Data-rich dashboards.
- Interactive visualisations.
- Context-sensitive navigation.
- Consistent iconography.
- Skeleton loading and empty states.
- Responsive sidebars and mobile navigation.
- Accessibility and readable typography.
- Cohesive branding without sacrificing usability.

These capabilities are integrated into the operating instructions and relevant design sections. They are guidance; they do not claim every existing app already supports each capability.
```


---

## SOURCE FILE: `08_UX_ARCHITECTURE/INSTRUCT.md`

```markdown
---
title: UX Architecture
type: ui-standard
updated: 2026-11-22
author: "Luke Nallen"
---

# UX Architecture

## Information architecture
Group features by user goals and mental models, not internal code ownership. Keep navigation labels concrete and stable. Use progressive disclosure to prevent overwhelming first-time users.

## Navigation
Choose the simplest model that fits: top navigation for a few peer areas; sidebar for many persistent workspaces; tabs for peer views within one context; breadcrumbs for deep hierarchies; command palette for power users. Avoid multiple competing navigation systems.

## User journeys
For each key task document: entry point, prerequisites, steps, decision points, success state, failure/recovery path and exit. Reduce unnecessary steps while retaining confirmations for high-impact actions.

## Accessibility
Use semantic landmarks and headings, correctly labelled controls, meaningful link text, keyboard access, visible focus, screen-reader status announcements and sufficient contrast. Do not rely on colour, position, sound or animation alone.

## Usability
Test with representative tasks. Measure task completion, time, errors, recovery and user confidence. Ask users to think aloud; observe confusion rather than explaining the interface. Fix high-frequency/high-impact friction first.

## Trust and transparency
Show data provenance, last updated time, permission boundaries and system status where relevant. Distinguish suggestions, recorded facts, simulations and executed actions.
```


---

## SOURCE FILE: `09_IMPLEMENTATION/CHATGPT_VISUAL_ADAPTER.md`

```markdown
---
title: ChatGPT Visual Rendering Adapter
version: 1.0.0
updated: 2026-11-23
status: host-adapter-specification
author: "Luke Nallen"
---

# ChatGPT Visual Rendering Adapter

## Purpose

Specify how the portable component library should be rendered inside ChatGPT conversations and compatible custom GPT experiences.

## Rendering priority

1. **Native interactive UI:** use supported ChatGPT visual components and controls when they can faithfully represent the requested interface and its behaviour.
2. **Structured visual composition:** use cards, grids, tables, charts, lists, tabs, status labels and interactive controls supported by the current host.
3. **Static visual:** if interaction is unavailable, show a clear static dashboard or visual layout.
4. **Markdown fallback:** use semantic headings, tables and lists only when visual composition is not supported.

Do not describe a static preview as a live application. Do not claim persistence, navigation, file access, notifications, chart updates or external actions unless the host actually provides them.

## Component mapping

| Library component | ChatGPT rendering approach |
|---|---|
| AppShell / DashboardFrame | Compose header, navigation and content sections |
| KPIGrid / MetricCard | Grid or card composition |
| StatusBadge | Badge or concise status text |
| PriorityQueue / TaskQueue | Structured list or table |
| AgentRoster / AgentCard | Responsive card grid |
| ChartPanel / LineChart / BarChart | Native chart when available; otherwise labelled static chart |
| SegmentBreakdown | Bar chart, table or labelled list |
| DataQualityCard | Status card with evidence and timestamp |
| ProjectHeader / ProgressCard | Header and progress composition |
| MilestoneList / ActivityFeed | Ordered list or timeline-style list |
| EditorShell / PropertiesPanel | Split composition when supported; otherwise stacked panels |
| AudioVisualizer / Waveform | Static waveform/diagram unless a real audio visualisation runtime is available |
| FilterBar | Native input, select, date and segmented controls |
| CommandPalette | Search input and command list; only live if callbacks exist |

## Interaction rules

- Inputs that affect visible content must be controlled by shared state.
- Buttons and links must perform the action advertised.
- Do not render inert controls as if they are functional.
- Use callbacks only where the host exposes a real action.
- Distinguish local UI state from persisted source data.
- Confirm consequential mutations through the host before showing success.
- Keep unavailable controls hidden or explicitly disabled with an explanation.

## Data rules

- Bind displayed values to source data where the host provides structured bindings.
- Do not copy or invent metrics merely to make a dashboard look populated.
- For mockups, use clearly labelled sample data and include a visible illustrative-data disclosure.
- Display unknown values as unavailable rather than filling them with plausible values.
- Show source freshness only when the host can establish it.

## Visual rules

- Apply the selected theme preset consistently across all components.
- Maintain spacing, typography, border, radius and status-token consistency.
- Use responsive card grids and preserve reading order.
- Prefer concise section titles and meaningful hierarchy.
- Respect accessibility, keyboard interaction and reduced motion.
- Use a visual component for information when it materially improves comprehension; avoid decorative visuals that add no value.

## Host limitations

The exact set of renderable controls varies by ChatGPT surface, model, account, workspace and available tools. A knowledge archive does not install executable components into ChatGPT. It supplies reusable specifications and instructions. Each account must upload or otherwise access the archive, and each target runtime must provide or implement the required adapter.

## Verification checklist

- [ ] Correct component and theme selected.
- [ ] All values source-backed or labelled illustrative.
- [ ] No inert controls presented as functional.
- [ ] Responsive reading order preserved.
- [ ] Missing or unavailable host capabilities disclosed.
- [ ] Visual representation preferred over plain Markdown when supported.
```


---

## SOURCE FILE: `09_IMPLEMENTATION/INSTRUCT.md`

```markdown
---
title: Implementation
type: ui-standard
updated: 2026-11-22
author: "Luke Nallen"
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
```


---

## SOURCE FILE: `09_IMPLEMENTATION/markdown_dashboard_renderer.md`

```markdown
---
title: Markdown Document and Dashboard Renderer
component: MarkdownDocumentRenderer
version: 1.0
updated: 2026-11-23
status: reusable-integration-pattern
author: "Luke Nallen"
---

# Markdown Document and Dashboard Renderer

## Purpose

A reusable rendering pattern for presenting an existing Markdown document as a navigable application view rather than a plain-text summary. `MarkdownDashboardRenderer` is the dashboard-oriented composition of `MarkdownDocumentRenderer`.

This is an integration contract, not a mandate to add a particular framework or dependency. Use the host application's native Markdown renderer where one exists. Keep the renderer separate from source storage, domain logic and application-specific visual configuration.

## Composition

The renderer composes existing library components instead of redefining them:

- `DashboardFrame` — page measure, padding and section rhythm.
- `PageHeader` / `SectionHeader` — document identity and hierarchy.
- `MetricTile` — compact numeric or categorical snapshots when the source supports them.
- `Alert` / `Callout` — semantic notices and contextual disclosures.
- `DataTable` — source tables with responsive overflow or an intentional mobile alternative.
- `Accordion` — progressive disclosure for secondary material.
- `NavigationLink` — genuine links to related source documents.
- `ReadOnlyBanner` — visible disclosure when the view is non-mutating.
- `EmptyState` / `ErrorState` — missing source and rendering failure.

## Required inputs

```ts
type MarkdownDocumentRendererProps = {
  sourceId: string;                 // stable host-native document identifier
  title?: string;
  mode?: "document" | "dashboard";
  readOnly?: boolean;               // defaults to true for dashboard previews
  refreshKey?: string | number;
  onNavigate?: (destination: string) => void;
  renderMarkdown: (source: string, context: RenderContext) => RenderResult;
  loadSource: (sourceId: string) => Promise<string>;
};

type RenderContext = {
  sourceId: string;
  resolveInternalLinks: true;
  allowEmbeds: boolean;
  readOnly: boolean;
};
```

The host adapter owns `loadSource`, native Markdown parsing, internal-link resolution and lifecycle cleanup. The component must not guess file paths or convert internal links into unverified URLs.

## Behaviour contract

1. Load the canonical Markdown source without modifying it.
2. Render Markdown using the host-native parser where available, preserving headings, lists, tables, blockquotes, callouts/admonitions, code blocks, embeds and collapsible sections supported by that host.
3. Resolve internal links against the original source context so relative paths and wiki-link semantics remain valid.
4. Keep external links distinguishable from internal navigation and apply the host's normal permission and confirmation behaviour.
5. Re-render on explicit refresh or source-change events; cancel or ignore stale asynchronous renders.
6. Unload observers, subscriptions and renderer components when the view closes.
7. Never write, create, rename, delete or mutate source documents in read-only mode. Do not expose edit actions in the dashboard view.
8. Display an actionable error state if the source is missing or rendering fails; never silently substitute a summary.

## Read-only guarantee

`readOnly` is a capability boundary, not merely a visual label. The adapter must not call host write APIs, and any navigation target must be opened through the host's standard read-only navigation path. If a host cannot guarantee read-only behaviour, it must report that limitation instead of claiming the view is read-only.

## Rendering and fidelity requirements

- Preserve source hierarchy and content order; do not rewrite the Markdown as part of rendering.
- Render host-native callouts/admonitions with their semantic type and title.
- Render tables as semantic tables with header associations; provide horizontal scrolling or a documented stacked alternative on narrow screens.
- Render collapsible Markdown sections using accessible disclosure controls with keyboard support.
- Internal links must remain functional host-native links, not decorative buttons.
- Preserve code formatting and language labels where supported.
- Do not invent values, freshness, clinical interpretation or other data absent from the source.
- Show provenance and record currency where they exist in the source.

## States

| State | Required presentation |
|---|---|
| Loading | Stable frame and non-misleading loading indicator |
| Ready | Native Markdown output in the dashboard frame |
| Empty | Explain that the source has no content; do not fabricate dashboard data |
| Missing | Show the unresolved source identifier and recovery guidance |
| Error | Show render failure without discarding the source |
| Stale | Indicate source freshness only when the host can establish it |
| Read-only | Persistent disclosure and no mutation controls |

## Accessibility and responsive behaviour

- Preserve semantic heading levels and landmark structure.
- Keep link destinations and labels accessible to assistive technology.
- Ensure all disclosures and navigation work by keyboard with visible focus.
- Maintain text contrast in light, dark and high-contrast themes.
- Keep reading order identical to visual order.
- At mobile widths, constrain page padding, allow tables to scroll intentionally and avoid horizontal page overflow.
- Respect `prefers-reduced-motion`.

## Host adapter: Obsidian

The Obsidian adapter should use the public `MarkdownRenderer` API with the source file path as the render context. This is necessary for Obsidian callouts, internal wiki links, embeds and vault-relative links to resolve correctly. A custom `ItemView` can provide the dashboard frame and a dedicated content target. The adapter should unload its `Component` on refresh/close, watch only the canonical source for updates, and expose open/refresh commands.

For a read-only Obsidian dashboard, the adapter should only call vault read APIs and `MarkdownRenderer.render`; it must not call `vault.modify`, `vault.create`, `vault.delete`, `vault.rename` or other write APIs. Keep plugin-specific code in the target vault, not in this generic library. The library documents the contract and reusable primitives only.

## Examples of reuse

- A medication log dashboard: historical record, callouts, metric tiles, linked source records; sensitive values remain source-backed and unaltered.
- A project operations dashboard: project status, task tables, expandable notes and links to canonical project records.
- A research notebook dashboard: evidence summary, semantic notices, tables and references to source notes.

These examples share the renderer and primitives; each application supplies its own source, content and thin theme configuration.

## Verification checklist

- [ ] Source loaded from the canonical identifier.
- [ ] Source content remains unchanged after opening and refreshing.
- [ ] Internal links resolve in host context.
- [ ] Callouts/admonitions render with semantic type.
- [ ] Tables remain usable at mobile widths.
- [ ] Collapsible sections are keyboard accessible.
- [ ] Missing-source and render-error states are visible.
- [ ] Refresh does not duplicate content or subscriptions.
- [ ] Close/unmount releases listeners and renderer resources.
- [ ] No host write API is called in read-only mode.
```


---

## SOURCE FILE: `10_TEMPLATES/INSTRUCT.md`

```markdown
---
title: Templates
type: ui-standard
updated: 2026-11-22
author: "Luke Nallen"
---

# Templates

## Application shell
- Brand mark and product name.
- Primary navigation with current-location state.
- Workspace/context switcher when needed.
- Main content region with consistent max-width and spacing.
- Optional contextual inspector.
- Responsive mobile navigation and keyboard shortcuts.

## Analytics dashboard
- Date/filter controls.
- KPI strip with definitions and comparison context.
- Primary chart sized for the key question.
- Breakdown table or secondary visualisation.
- Data freshness, source and empty/error states.

## Operations dashboard
- Queue/status summary.
- Priority work list.
- Task detail/inspector.
- Activity and execution history.
- Clear approval, retry and handoff controls.

## Editor/workbench
- Project/file navigation.
- Central editor or canvas.
- Contextual properties panel.
- Preview/output area.
- Save/sync/run status and recovery from errors.

## Landing/onboarding
- Clear value proposition and primary action.
- Short explanation of how it works.
- Trust/provenance information where relevant.
- Progressive setup rather than a long upfront form.
- Accessible responsive layout.

## Settings
- Group settings by user mental model.
- Explain consequences for important options.
- Provide save/cancel feedback and reset paths.
- Do not expose internal or unsafe configuration unnecessarily.

Templates are starting points. Remove sections that do not serve the product's actual user journey.
```


---

## SOURCE FILE: `11_QUALITY_CONTROL/INSTRUCT.md`

```markdown
---
title: Quality Control
type: ui-standard
updated: 2026-11-22
author: "Luke Nallen"
---

# Quality Control

## Review gates
### Visual
- [ ] Clear hierarchy and focal point.
- [ ] Consistent typography, spacing, alignment and iconography.
- [ ] Colour and contrast work in light and dark modes.
- [ ] Effects are restrained and do not reduce readability.
- [ ] Realistic content fits without clipping or awkward wrapping.

### Functional
- [ ] Every visible control performs its labelled action.
- [ ] Loading, empty, success, warning and error states work.
- [ ] Forms validate and explain errors.
- [ ] Navigation, back behaviour and deep links work.
- [ ] Data shown matches its source and freshness.

### Responsive
- [ ] Narrow phone, tablet, desktop and wide layouts checked.
- [ ] No horizontal overflow except intentional data regions.
- [ ] Touch targets and keyboard use are practical.
- [ ] Dialogs and virtual keyboards do not trap content.

### Accessibility
- [ ] Semantic structure and labels.
- [ ] Keyboard navigation and visible focus.
- [ ] Contrast and non-colour status cues.
- [ ] Reduced motion and screen-reader announcements.
- [ ] Charts have text alternatives.

### Engineering
- [ ] Lint/typecheck/tests/build run where available.
- [ ] No console errors or broken assets.
- [ ] No secrets or sensitive data exposed.
- [ ] Existing workflows and business logic preserved.
- [ ] Dependencies and browser support verified.

## Severity
- `P0`: data loss, security issue, blocked core task.
- `P1`: major workflow broken or severe accessibility failure.
- `P2`: significant usability/visual inconsistency.
- `P3`: minor polish or low-impact issue.

## Audit report
Record scope, app version/commit, viewport, browsers/devices, findings, severity, reproduction steps, evidence, owner, fix and retest result. Mark untested items explicitly.
```


---

## SOURCE FILE: `12_APP_PROFILES/COMMERCE_EXPERIENCE_PROFILE.md`

```markdown
---
author: "Luke Nallen"
---

# Commerce Experience Profile

## Purpose
Product discovery, catalogues, storefronts, subscriptions and purchasing journeys.

## Primary user jobs
Help users discover, evaluate and select offerings with transparent pricing and clear transaction states.

## Suggested information architecture
Store header/navigation, category/search controls, product cards, comparison/detail view, basket/selection summary and checkout steps.

## Reusable component families
- Navigation, breadcrumbs and contextual actions.
- Cards, lists, tables, tabs and responsive content grids.
- Search, filtering, sorting and forms where relevant.
- Status, progress, empty, loading, error and confirmation states.
- Accessible dialogs, menus, tooltips and notifications where supported.

## Theme options
Light Product; Neutral Product; Warm Editorial

Choose the theme independently according to the content, environment, user preference and contrast requirements. Do not bind this profile to a single preset.

## Data and integration boundary
The host application supplies all data, business rules, authentication, permissions, persistence, APIs and external integrations. This profile defines presentation only and has no mandatory resource or runtime dependency.

## Responsive and accessibility requirements
- Start with a narrow mobile layout; progressively enhance for tablet and desktop.
- Reflow sidebars and multi-column regions without hiding essential information.
- Provide semantic headings, labels, keyboard access, visible focus and sufficient contrast.
- Pair status colours with text or icons; do not rely on colour alone.
- Respect reduced-motion settings and provide non-animated alternatives.

## States to define
Specify realistic loading, empty, error, permission-denied, offline/stale, success and destructive-confirmation states as applicable. Do not claim a state exists unless the host supplies it.

## Customisation boundary
The host may supply its product name, logo, approved brand tokens, terminology and domain-specific content. Keep those overrides outside this generic profile and shared component definitions.

## Evidence status
DOCUMENTED — reusable composition guidance; not an executable application or implementation claim.
```


---

## SOURCE FILE: `12_APP_PROFILES/CREATIVE_STUDIO_PROFILE.md`

```markdown
---
author: "Luke Nallen"
---

# Creative Studio Profile

## Purpose
Audio, video, visual design, writing production and other creative tools.

## Primary user jobs
Keep the creation surface central while making tools, assets and properties discoverable.

## Suggested information architecture
Project header, canvas/timeline/editor, tool rail, asset browser, inspector/properties panel, preview and version history.

## Reusable component families
- Navigation, breadcrumbs and contextual actions.
- Cards, lists, tables, tabs and responsive content grids.
- Search, filtering, sorting and forms where relevant.
- Status, progress, empty, loading, error and confirmation states.
- Accessible dialogs, menus, tooltips and notifications where supported.

## Theme options
Creative Studio; Neutral Product; High Contrast

Choose the theme independently according to the content, environment, user preference and contrast requirements. Do not bind this profile to a single preset.

## Data and integration boundary
The host application supplies all data, business rules, authentication, permissions, persistence, APIs and external integrations. This profile defines presentation only and has no mandatory resource or runtime dependency.

## Responsive and accessibility requirements
- Start with a narrow mobile layout; progressively enhance for tablet and desktop.
- Reflow sidebars and multi-column regions without hiding essential information.
- Provide semantic headings, labels, keyboard access, visible focus and sufficient contrast.
- Pair status colours with text or icons; do not rely on colour alone.
- Respect reduced-motion settings and provide non-animated alternatives.

## States to define
Specify realistic loading, empty, error, permission-denied, offline/stale, success and destructive-confirmation states as applicable. Do not claim a state exists unless the host supplies it.

## Customisation boundary
The host may supply its product name, logo, approved brand tokens, terminology and domain-specific content. Keep those overrides outside this generic profile and shared component definitions.

## Evidence status
DOCUMENTED — reusable composition guidance; not an executable application or implementation claim.
```


---

## SOURCE FILE: `12_APP_PROFILES/DATA_WORKBENCH_PROFILE.md`

```markdown
---
author: "Luke Nallen"
---

# Data Workbench Profile

## Purpose
Analytics, reporting, monitoring, research and data exploration applications.

## Primary user jobs
Help users inspect evidence, compare values, identify changes and understand data quality.

## Suggested information architecture
Data source/context bar, KPI summary, filters, chart/table workspace, insight notes, data freshness and export actions.

## Reusable component families
- Navigation, breadcrumbs and contextual actions.
- Cards, lists, tables, tabs and responsive content grids.
- Search, filtering, sorting and forms where relevant.
- Status, progress, empty, loading, error and confirmation states.
- Accessible dialogs, menus, tooltips and notifications where supported.

## Theme options
Data Workbench; Light Product; High Contrast

Choose the theme independently according to the content, environment, user preference and contrast requirements. Do not bind this profile to a single preset.

## Data and integration boundary
The host application supplies all data, business rules, authentication, permissions, persistence, APIs and external integrations. This profile defines presentation only and has no mandatory resource or runtime dependency.

## Responsive and accessibility requirements
- Start with a narrow mobile layout; progressively enhance for tablet and desktop.
- Reflow sidebars and multi-column regions without hiding essential information.
- Provide semantic headings, labels, keyboard access, visible focus and sufficient contrast.
- Pair status colours with text or icons; do not rely on colour alone.
- Respect reduced-motion settings and provide non-animated alternatives.

## States to define
Specify realistic loading, empty, error, permission-denied, offline/stale, success and destructive-confirmation states as applicable. Do not claim a state exists unless the host supplies it.

## Customisation boundary
The host may supply its product name, logo, approved brand tokens, terminology and domain-specific content. Keep those overrides outside this generic profile and shared component definitions.

## Evidence status
DOCUMENTED — reusable composition guidance; not an executable application or implementation claim.
```


---

## SOURCE FILE: `12_APP_PROFILES/EDITORIAL_CONTENT_PROFILE.md`

```markdown
---
author: "Luke Nallen"
---

# Editorial Content Profile

## Purpose
Reading, documentation, publishing, knowledge bases and long-form content.

## Primary user jobs
Prioritise readability, hierarchy, navigation through content and clear editorial status.

## Suggested information architecture
Document title and metadata, contents/navigation, reading or editing column, annotations, related resources and publishing controls.

## Reusable component families
- Navigation, breadcrumbs and contextual actions.
- Cards, lists, tables, tabs and responsive content grids.
- Search, filtering, sorting and forms where relevant.
- Status, progress, empty, loading, error and confirmation states.
- Accessible dialogs, menus, tooltips and notifications where supported.

## Theme options
Warm Editorial; Light Product; High Contrast

Choose the theme independently according to the content, environment, user preference and contrast requirements. Do not bind this profile to a single preset.

## Data and integration boundary
The host application supplies all data, business rules, authentication, permissions, persistence, APIs and external integrations. This profile defines presentation only and has no mandatory resource or runtime dependency.

## Responsive and accessibility requirements
- Start with a narrow mobile layout; progressively enhance for tablet and desktop.
- Reflow sidebars and multi-column regions without hiding essential information.
- Provide semantic headings, labels, keyboard access, visible focus and sufficient contrast.
- Pair status colours with text or icons; do not rely on colour alone.
- Respect reduced-motion settings and provide non-animated alternatives.

## States to define
Specify realistic loading, empty, error, permission-denied, offline/stale, success and destructive-confirmation states as applicable. Do not claim a state exists unless the host supplies it.

## Customisation boundary
The host may supply its product name, logo, approved brand tokens, terminology and domain-specific content. Keep those overrides outside this generic profile and shared component definitions.

## Evidence status
DOCUMENTED — reusable composition guidance; not an executable application or implementation claim.
```


---

## SOURCE FILE: `12_APP_PROFILES/GENERAL_APPLICATION_PROFILE.md`

```markdown
---
author: "Luke Nallen"
---

# General Application Profile

## Purpose
General-purpose SaaS, productivity tools, settings-driven products and multi-purpose applications.

## Primary user jobs
Orient users, expose primary tasks, show current context and provide predictable navigation.

## Suggested information architecture
Header, primary navigation, page title, contextual actions, overview cards, content region, settings and help.

## Reusable component families
- Navigation, breadcrumbs and contextual actions.
- Cards, lists, tables, tabs and responsive content grids.
- Search, filtering, sorting and forms where relevant.
- Status, progress, empty, loading, error and confirmation states.
- Accessible dialogs, menus, tooltips and notifications where supported.

## Theme options
Neutral Product; Light Product; High Contrast

Choose the theme independently according to the content, environment, user preference and contrast requirements. Do not bind this profile to a single preset.

## Data and integration boundary
The host application supplies all data, business rules, authentication, permissions, persistence, APIs and external integrations. This profile defines presentation only and has no mandatory resource or runtime dependency.

## Responsive and accessibility requirements
- Start with a narrow mobile layout; progressively enhance for tablet and desktop.
- Reflow sidebars and multi-column regions without hiding essential information.
- Provide semantic headings, labels, keyboard access, visible focus and sufficient contrast.
- Pair status colours with text or icons; do not rely on colour alone.
- Respect reduced-motion settings and provide non-animated alternatives.

## States to define
Specify realistic loading, empty, error, permission-denied, offline/stale, success and destructive-confirmation states as applicable. Do not claim a state exists unless the host supplies it.

## Customisation boundary
The host may supply its product name, logo, approved brand tokens, terminology and domain-specific content. Keep those overrides outside this generic profile and shared component definitions.

## Evidence status
DOCUMENTED — reusable composition guidance; not an executable application or implementation claim.
```


---

## SOURCE FILE: `12_APP_PROFILES/INSTRUCT.md`

```markdown
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
```


---

## SOURCE FILE: `12_APP_PROFILES/OPERATIONS_WORKSPACE_PROFILE.md`

```markdown
---
author: "Luke Nallen"
---

# Operations Workspace Profile

## Purpose
Task management, workflow orchestration, service operations and approvals.

## Primary user jobs
Make current work, ownership, blockers, next actions and audit context immediately clear.

## Suggested information architecture
Status summary, queue/list, filters, owner and due-date metadata, workflow detail, activity log, approval/action area.

## Reusable component families
- Navigation, breadcrumbs and contextual actions.
- Cards, lists, tables, tabs and responsive content grids.
- Search, filtering, sorting and forms where relevant.
- Status, progress, empty, loading, error and confirmation states.
- Accessible dialogs, menus, tooltips and notifications where supported.

## Theme options
Data Workbench; Neutral Product; High Contrast

Choose the theme independently according to the content, environment, user preference and contrast requirements. Do not bind this profile to a single preset.

## Data and integration boundary
The host application supplies all data, business rules, authentication, permissions, persistence, APIs and external integrations. This profile defines presentation only and has no mandatory resource or runtime dependency.

## Responsive and accessibility requirements
- Start with a narrow mobile layout; progressively enhance for tablet and desktop.
- Reflow sidebars and multi-column regions without hiding essential information.
- Provide semantic headings, labels, keyboard access, visible focus and sufficient contrast.
- Pair status colours with text or icons; do not rely on colour alone.
- Respect reduced-motion settings and provide non-animated alternatives.

## States to define
Specify realistic loading, empty, error, permission-denied, offline/stale, success and destructive-confirmation states as applicable. Do not claim a state exists unless the host supplies it.

## Customisation boundary
The host may supply its product name, logo, approved brand tokens, terminology and domain-specific content. Keep those overrides outside this generic profile and shared component definitions.

## Evidence status
DOCUMENTED — reusable composition guidance; not an executable application or implementation claim.
```


---

## SOURCE FILE: `12_APP_PROFILES/PROJECT_WORKSPACE_PROFILE.md`

```markdown
---
author: "Luke Nallen"
---

# Project Workspace Profile

## Purpose
Project planning, team collaboration, milestones, deliverables and progress tracking.

## Primary user jobs
Connect goals, workstreams, milestones, tasks, files and decisions in one navigable context.

## Suggested information architecture
Project identity/context, progress overview, milestone timeline, task board/list, team/roles, files, decisions and activity.

## Reusable component families
- Navigation, breadcrumbs and contextual actions.
- Cards, lists, tables, tabs and responsive content grids.
- Search, filtering, sorting and forms where relevant.
- Status, progress, empty, loading, error and confirmation states.
- Accessible dialogs, menus, tooltips and notifications where supported.

## Theme options
Neutral Product; Light Product; Creative Studio

Choose the theme independently according to the content, environment, user preference and contrast requirements. Do not bind this profile to a single preset.

## Data and integration boundary
The host application supplies all data, business rules, authentication, permissions, persistence, APIs and external integrations. This profile defines presentation only and has no mandatory resource or runtime dependency.

## Responsive and accessibility requirements
- Start with a narrow mobile layout; progressively enhance for tablet and desktop.
- Reflow sidebars and multi-column regions without hiding essential information.
- Provide semantic headings, labels, keyboard access, visible focus and sufficient contrast.
- Pair status colours with text or icons; do not rely on colour alone.
- Respect reduced-motion settings and provide non-animated alternatives.

## States to define
Specify realistic loading, empty, error, permission-denied, offline/stale, success and destructive-confirmation states as applicable. Do not claim a state exists unless the host supplies it.

## Customisation boundary
The host may supply its product name, logo, approved brand tokens, terminology and domain-specific content. Keep those overrides outside this generic profile and shared component definitions.

## Evidence status
DOCUMENTED — reusable composition guidance; not an executable application or implementation claim.
```


---

## SOURCE FILE: `12_APP_PROFILES/RESOURCE_LIBRARY_PROFILE.md`

```markdown
---
author: "Luke Nallen"
---

# Resource Library Profile

## Purpose
File managers, asset libraries, document repositories and searchable knowledge collections.

## Primary user jobs
Support fast discovery, clear provenance, preview and safe resource actions.

## Suggested information architecture
Search and filters, collection navigation, resource list/grid, metadata panel, preview, version/provenance and import/export actions.

## Reusable component families
- Navigation, breadcrumbs and contextual actions.
- Cards, lists, tables, tabs and responsive content grids.
- Search, filtering, sorting and forms where relevant.
- Status, progress, empty, loading, error and confirmation states.
- Accessible dialogs, menus, tooltips and notifications where supported.

## Theme options
Neutral Product; Light Product; Data Workbench

Choose the theme independently according to the content, environment, user preference and contrast requirements. Do not bind this profile to a single preset.

## Data and integration boundary
The host application supplies all data, business rules, authentication, permissions, persistence, APIs and external integrations. This profile defines presentation only and has no mandatory resource or runtime dependency.

## Responsive and accessibility requirements
- Start with a narrow mobile layout; progressively enhance for tablet and desktop.
- Reflow sidebars and multi-column regions without hiding essential information.
- Provide semantic headings, labels, keyboard access, visible focus and sufficient contrast.
- Pair status colours with text or icons; do not rely on colour alone.
- Respect reduced-motion settings and provide non-animated alternatives.

## States to define
Specify realistic loading, empty, error, permission-denied, offline/stale, success and destructive-confirmation states as applicable. Do not claim a state exists unless the host supplies it.

## Customisation boundary
The host may supply its product name, logo, approved brand tokens, terminology and domain-specific content. Keep those overrides outside this generic profile and shared component definitions.

## Evidence status
DOCUMENTED — reusable composition guidance; not an executable application or implementation claim.
```


---

## SOURCE FILE: `13_PATTERN_LIBRARY/INSTRUCT.md`

```markdown
---
author: "Genesis"
generated_by: "Genesis"
---
# Pattern Library

Reusable interaction and composition patterns gathered from available project and conversation history. Patterns are domain-neutral; examples retain their source context.

Each pattern must state purpose, composition, data contract, interaction contract, responsive behaviour, accessibility, empty/loading/error states, and limitations.
```


---

## SOURCE FILE: `13_PATTERN_LIBRARY/PATTERN_CATALOG.md`

```markdown
---
author: "Genesis"
generated_by: "Genesis"
---
# Universal UI Pattern Catalogue

## Application and workspace patterns
- **Command centre:** operational status, priority queue, alerts, recent activity and quick actions.
- **Workspace switcher:** switch among projects, environments or workspaces without confusing identity or permissions.
- **Multi-tab workspace:** preserve context across open resources; disclose unsaved changes before closing.
- **Split workspace:** primary work surface plus contextual inspector; stack on narrow screens.
- **Resource browser:** searchable, filterable collection with preview, metadata and version history.
- **Document dashboard:** document navigation, source content, contextual metadata and related resources.
- **Project overview:** purpose, status, milestones, tasks, dependencies, files and activity.
- **Operations board:** grouped work queues, owners, status, priority and due dates.
- **Approval queue:** pending decision, evidence, requester, impact, decision actions and audit trail.

## Data and analytical patterns
- KPI overview with definition, unit, period, source and comparison baseline.
- Filter → segment → inspect → export workflow.
- Metric drill-down from summary to underlying records.
- Data quality and freshness panel.
- Scenario comparison with baseline, intervention and outcome.
- Forecast panel with assumptions, uncertainty and confidence labels.
- Network/relationship graph with selected-node inspector.
- Event timeline and time-series comparison.
- Provenance panel separating observed, inferred, estimated and unknown values.

## Agent and automation patterns
- Agent roster with role, capability, availability and current assignment.
- Agent detail inspector with instructions, tools, permissions and execution history.
- Workflow canvas with typed nodes, edges, branches and validation.
- Trigger configuration with event, condition, scope, schedule and action.
- Task manifest with owner, dependencies, acceptance criteria and status.
- Execution console with step log, outputs, errors, retries and cancellation.
- Human approval gate for consequential actions.
- Retry/resume panel that preserves completed steps and records recovery.
- Chain-of-command view showing delegation, escalation and responsibility.
- Run comparison showing configuration/version and output differences.

## Knowledge and document patterns
- Library index with taxonomy, tags, search and filters.
- Document reader with table of contents, section anchors and citations.
- Source comparison and diff view.
- Metadata editor with validation and provenance.
- Research pipeline: intake → triage → extraction → synthesis → review → release.
- Evidence ledger with source, claim, confidence, date and supporting excerpt.
- Release candidate panel with validation findings and blockers.
- Book/manuscript workflow with chapter structure, editorial status, revision and proofing gates.

## Creative and media patterns
- Editor shell with tool rail, canvas, inspector and timeline.
- Layer/track list with visibility, mute, lock and ordering.
- Asset browser with preview, metadata and import state.
- Audio waveform/spectrum with playhead and selection.
- Preset browser and non-destructive parameter inspector.
- Version comparison and export queue.
- Creative brief → draft → review → revision → delivery flow.

## Commerce and service patterns
- Product catalogue, category navigation, filters and comparison.
- Product detail with options, availability and transparent pricing.
- Cart/checkout stepper with validation and order summary.
- Store operations dashboard with orders, fulfilment, stock and exceptions.
- Multi-location overview with location-level drill-down.
- Customer support queue with SLA, owner, status and conversation history.

## Learning and behavioural patterns
- Interactive concept explorer with node-specific detail.
- Stepwise learning path and progress checkpoints.
- Reflection prompt and journal capture.
- Scenario simulator with explicit assumptions and repeatable inputs.
- Before/after comparison that distinguishes measured from hypothetical outcomes.
- Progression tree with locked/unlocked state only when backed by actual rules.

## Interface state patterns
All interactive surfaces should specify: initial, loading, ready, empty, filtered-empty, error, offline, stale, disabled, permission-denied, submitting, success-confirmed and partial-success states where relevant.
```


---

## SOURCE FILE: `14_DOMAIN_INTERFACE_BLUEPRINTS/BLUEPRINTS.md`

```markdown
---
author: "Genesis"
generated_by: "Genesis"
---
# Domain Interface Blueprints

## 1. Interactive system / behavioural model explorer
**Conversation source:** Karma Circle / Behaviour OS discussions, including KC-MV24 and Perceptual Veil.

Composition:
- Framework title/header and concise explanatory context.
- Primary circular or network visualization.
- Sequential flow / propagation view.
- Selected-node inspector.
- Scenario input and simulation controls.
- Baseline versus intervention comparison.
- History/repetition panel and linked research references.

Node inspector content contract:
- Node identity and stage.
- Definition and role in the model.
- Current value/state and calibration label.
- Upstream inputs and downstream effects.
- Explanation and real-world example.
- Common misconception.
- Available intervention(s).
- Reflection exercise.
- Canonical next-node transition.

Model visualization requirements:
- Support ordered stages and graph relationships.
- Highlight selected, upstream, downstream and changed nodes.
- Show before/after state and intervention path.
- Preserve reproducibility by displaying scenario inputs and model version.
- Distinguish reported, inferred, uncertain and repeated observations.
- Do not imply a psychological inference is a verified fact.

Example pipeline retained from prior project discussions:
Stimulus → Identity → Perceptual Veil → Predictions → Weighting → Attention → Reality → Behaviour → Action → Emotion → Memory → Echo → Social → Identity.
This is a source-specific example, not a universal model.

## 2. Research operations workspace
**Conversation source:** Ascension Research dashboard and research pipeline discussions.

Composition:
- Project summary and research status.
- Trigger/instruction overview.
- Active and completed research navigation.
- Research intake and staging.
- Source/evidence register.
- Draft synthesis and review queue.
- Final-pass writer/reviewer panel.
- Release candidates and validation results.
- Research logs and decision history.

Workflow states should be configurable; never infer that a stage is complete without evidence.

## 3. Agent and workflow orchestration workspace
**Conversation source:** Genesis Forge, AgentMaster, Questmaster, File Warden and workflow/agent trigger discussions.

Composition:
- Project/workspace selector.
- Agent roster and role/capability cards.
- Workflow canvas and chain-of-command view.
- Trigger registry and configuration.
- Task ledger and task template.
- Assignment/dependency panel.
- Execution log, validation and retry/resume.
- File/resource operations and provenance.
- Release/approval gate.

Keep agent definition, trigger definition, workflow definition and task record as distinct entities. Do not merge their contracts.

## 4. Local application builder
**Conversation source:** LocalForge and A.I Master product discussions.

Composition:
- Project/file explorer.
- Code/editor surface.
- Live preview region.
- Runtime/server status.
- Console and error panel.
- Dependency/library selector.
- Run/stop controls.
- Build history and version comparison.

A preview is not proof of a successful build. Distinguish editor state, runtime state and deployment state.

## 5. Book and manuscript production
**Conversation source:** BookMaster and publishing-stage discussions.

Composition:
- Book/project overview.
- Manuscript/chapter navigator.
- Draft editor and document preview.
- Editorial issue list.
- Author/editor comments.
- Revision history and comparison.
- Proofreading checklist and approval gate.
- Export/package readiness.

Keep proofreading separate from substantive editing, copyediting and final production unless the workflow owner explicitly combines them.

## 6. Multi-location commerce / restaurant operations
**Conversation source:** Pizza Hub business planning.

Composition:
- Brand/location overview.
- Sales and order channels.
- Menu/catalogue editor.
- Orders and fulfilment queue.
- Stock and supplier status.
- Location comparison.
- Staff/shift planning.
- Customer feedback and issue queue.

This is a reusable restaurant operations composition, not a claim that the source project has live operational data.

## 7. Behavioural learning / progression interface
**Conversation source:** Karma Circle training quests and Behaviour OS progression discussions.

Reusable modules:
- Awareness, identity, resonance and behaviour indicators.
- Current/best streak and weekly score.
- Quest list and completion state.
- Skill/evolution tree.
- Trajectory forecast with assumptions.
- Behaviour archetype cards.
- Identity-state selector where the underlying application defines valid options.

Use only source-backed values. Forecasts must show their assumptions and uncertainty.
```


---

## SOURCE FILE: `14_DOMAIN_INTERFACE_BLUEPRINTS/INSTRUCT.md`

```markdown
---
author: "Genesis"
generated_by: "Genesis"
---
# Domain Interface Blueprints

These blueprints translate recurring project requirements from prior conversations into reusable UI compositions. They are examples and must not hard-code project data, brands or business rules.
```


---

## SOURCE FILE: `15_FRAMEWORK_ADAPTERS/ADAPTER_AND_INGESTION_SPEC.md`

```markdown
---
author: "Genesis"
generated_by: "Genesis"
---
# Framework Adapter and User Library Ingestion Specification

## Supported source families
The library must support user-supplied design systems, component libraries and templates including:
- Bootstrap
- React component libraries
- Tailwind CSS and utility conventions
- shadcn/ui
- Material UI
- Ant Design
- Custom CSS, design tokens, component packages and project templates

This is a source-ingestion requirement, not a claim that every framework is bundled or installed.

## Ingestion workflow
1. **Receive:** accept permitted source formats (repository/archive, CSS, JSON tokens, component documentation, templates).
2. **Inventory:** enumerate files, package metadata, versions, framework/runtime, license and dependencies.
3. **Classify:** identify tokens, components, primitives, layouts, patterns, examples and assets.
4. **Extract contracts:** props, events, slots, variants, states, accessibility and responsive behaviour.
5. **Normalize:** map source definitions to the framework-neutral component schema without destroying source terminology.
6. **Preserve provenance:** retain original package, version, path, source URL or archive name, license and extraction timestamp where available.
7. **Build manifest:** generate machine-readable inventory and dependency graph.
8. **Validate:** check parseability, missing dependencies, duplicate IDs, license constraints and broken references.
9. **Select:** allow a project to choose one or more compatible libraries/design systems.
10. **Compose:** generate the app using the selected source library; avoid silently mixing conflicting design systems.
11. **Report:** provide ingestion summary, warnings, unsupported files and unresolved dependencies.

## Required manifest fields
`id`, `name`, `source_type`, `source_version`, `framework`, `runtime`, `license`, `source_path`, `component_count`, `token_sets`, `dependencies`, `peer_dependencies`, `accessibility_notes`, `responsive_notes`, `ingestion_status`, `validation_findings`.

Unknown fields remain unknown. Do not invent license terms or infer compatibility from a package name alone.

## Project-level selection
Each project declares:
- selected component library/libraries;
- selected theme/token set;
- framework and runtime;
- allowed dependency versions;
- component overrides;
- adapter mapping;
- source provenance.

## Compatibility rules
- React component packages are not automatically compatible with non-React runtimes.
- Tailwind utility classes require the matching build/configuration pipeline.
- shadcn/ui components require their source code and expected dependencies; they are not a hosted component service.
- Bootstrap, Material UI and Ant Design have distinct styling and interaction conventions; avoid mixing them without an explicit integration plan.
- Custom templates retain their own license and attribution requirements.
- Never strip license files or attribution notices during ingestion.

## Output
Produce an inventory, normalized component manifest, adapter mapping, dependency report, license report and validation report. Keep source package and normalized library definitions traceable.
```


---

## SOURCE FILE: `15_FRAMEWORK_ADAPTERS/INSTRUCT.md`

```markdown
---
author: "Genesis"
generated_by: "Genesis"
---
# Framework and Design-System Adapters

The library is framework-neutral at its core. Adapters translate generic component contracts into a chosen implementation stack.
```


---

## SOURCE FILE: `16_COMPONENT_CONTRACTS/EXTENDED_COMPONENTS.md`

```markdown
---
author: "Genesis"
generated_by: "Genesis"
---
# Extended Component Contracts

| Component | Purpose | Key contract |
|---|---|---|
| `EvidenceLedger` | Claims and evidence | source, claim, excerpt, confidence, date, status |
| `ProvenanceViewer` | Data lineage | origin, transformations, version, author, timestamp |
| `ScenarioWorkbench` | Repeatable scenario runs | inputs, model version, assumptions, run ID, outputs |
| `BeforeAfterCompare` | Compare states | baseline, changed state, delta, explanation |
| `NodeInspector` | Inspect graph/model node | selected node, definition, values, relations, interventions |
| `NetworkCanvas` | Relationship visualization | nodes, edges, selection, layout, zoom |
| `WorkflowCanvas` | Workflow authoring | nodes, typed edges, branches, validation, execution state |
| `ExecutionTimeline` | Run history | ordered events, timestamps, status, outputs |
| `TaskManifest` | Structured task record | objective, scope, owner, dependencies, acceptance criteria |
| `ApprovalGate` | Human decision | request, evidence, risk, decision, actor, audit record |
| `RetryResumePanel` | Recovery | failed step, retry policy, checkpoint, prior outputs |
| `LibraryImporter` | Import UI libraries | source, inventory, license, dependencies, validation |
| `ComponentPicker` | Select reusable components | search, filters, compatibility, preview, selected version |
| `ThemePicker` | Select themes | preset, preview, contrast notes, brand overrides |
| `DesignTokenInspector` | Inspect tokens | token name, value, semantic role, source |
| `ResponsivePreview` | Preview breakpoints | viewport, layout mode, overflow warnings |
| `VersionDiff` | Compare versions | added, removed, changed, source and compatibility |
| `ReleaseChecklist` | Release readiness | requirement, evidence, result, blocker, reviewer |
| `ChapterNavigator` | Manuscript navigation | chapter, order, word count if supplied, editorial state |
| `EditorialIssueList` | Editing/proofing issues | location, category, severity, comment, resolution |
| `OrderQueue` | Commerce operations | order, channel, status, fulfilment, exception |
| `LocationComparison` | Multi-site operations | location, comparable metric, period, source |

Every contract must additionally define required/optional props, event signatures, state ownership, permission boundary, loading/empty/error/disabled states, keyboard behaviour, mobile layout and adapter availability.
```


---

## SOURCE FILE: `16_COMPONENT_CONTRACTS/INSTRUCT.md`

```markdown
---
author: "Genesis"
generated_by: "Genesis"
---
# Extended Component Contracts

New contracts must be framework-neutral, typed, testable and accompanied by states, accessibility and responsive rules.
```


---

## SOURCE FILE: `17_ACCESSIBILITY_RESPONSIVE/INSTRUCT.md`

```markdown
---
author: "Genesis"
generated_by: "Genesis"
---
# Accessibility and Responsive Standards
```


---

## SOURCE FILE: `17_ACCESSIBILITY_RESPONSIVE/STANDARDS.md`

```markdown
---
author: "Genesis"
generated_by: "Genesis"
---
# Accessibility and Responsive Standards

## Responsive
- Design mobile-first and reflow by available width.
- Never require page-level horizontal scrolling for primary workflows.
- Move sidebars to drawers or bottom navigation when appropriate.
- Preserve reading order when grids collapse.
- Keep primary actions reachable and avoid fixed overlays obscuring content.
- Tables should offer a deliberate narrow-screen alternative: stacked records, prioritized columns or controlled horizontal scrolling within the table region.

## Accessibility
- Use semantic landmarks and heading order.
- Every input has a programmatic label and clear validation.
- Icon-only actions require accessible names.
- Keyboard focus is visible and follows logical reading order.
- Status is not conveyed by colour alone.
- Respect reduced-motion preferences; motion must not be required to understand state.
- Charts need a text/table alternative and meaningful labels.
- Dialogs manage focus and return focus to their trigger.
- Touch targets should be comfortably operable.
- Contrast must be checked for text, controls and status indicators.

## Dense interfaces
- Provide compact and comfortable density modes where useful.
- Preserve units, labels and context in metric cards.
- Allow progressive disclosure rather than hiding critical context.
- Use truncation only when the full value remains discoverable.
```


---

## SOURCE FILE: `18_SOURCE_PROVENANCE/CONVERSATION_MATERIAL_INDEX.md`

```markdown
---
author: "Genesis"
generated_by: "Genesis"
---
# Conversation Material Index

## Scope and evidence
This index records reusable requirements recovered from available prior-conversation context and the uploaded 2.4.0 library. It is not a claim that every historical conversation or attachment has been exhaustively re-read. Project-specific details are generalized into patterns; exact source terminology is retained where useful.

| Source conversation/project | Reusable material incorporated | Destination |
|---|---|---|
| GPT UI Extension Library, 23–26 Nov 2026 | portable/resumable components, component families, themes, layouts, ChatGPT setup, library ingestion | core registries; framework adapters |
| User library ingestion, 26 Nov 2026 | Bootstrap, React, Tailwind, shadcn/ui, Material UI, Ant Design and custom templates; ingest/index/manifest/select per project | `15_FRAMEWORK_ADAPTERS/` |
| Karma Circle / Behaviour OS | circular model visualization, sequential flow, node inspector, scenario simulator, baseline/intervention comparison, recursive history, research links | `14_DOMAIN_INTERFACE_BLUEPRINTS/`, `16_COMPONENT_CONTRACTS/` |
| Ascension Research | project summary, triggers overview, active/completed research, staging, logs, release candidates, final-pass review | `14_DOMAIN_INTERFACE_BLUEPRINTS/` |
| Genesis Forge / AgentMaster | agent, trigger, skill, workflow and project generation; chain of command | `13_PATTERN_LIBRARY/`, `14_DOMAIN_INTERFACE_BLUEPRINTS/` |
| Questmaster | task ledger, templates, task records, agent execution and validation | `13_PATTERN_LIBRARY/`, `14_DOMAIN_INTERFACE_BLUEPRINTS/` |
| File Warden | file handling, resource registry, naming, metadata and provenance | `13_PATTERN_LIBRARY/`, `16_COMPONENT_CONTRACTS/` |
| LocalForge | file explorer, editor, live preview, runtime, logs, run/stop and project build | `14_DOMAIN_INTERFACE_BLUEPRINTS/` |
| BookMaster | manuscript/chapter navigation, editorial and proofreading stages | `14_DOMAIN_INTERFACE_BLUEPRINTS/` |
| Pizza Hub | budget/value restaurant and takeaway concept, scalable multi-location operations | `14_DOMAIN_INTERFACE_BLUEPRINTS/` |
| Karma Circle learning interface | quests, progression tree, streaks, trajectory forecast and identity-state selector | `14_DOMAIN_INTERFACE_BLUEPRINTS/` |

## Preservation rules
- Do not present source-specific models or terminology as universal facts.
- Do not invent implementation status, data, integrations, authentication or persistence.
- Keep app business logic and data schemas outside the standalone UI library.
- Retain source provenance and licensing when importing third-party frameworks.
```


---

## SOURCE FILE: `19_EXAMPLES/EXAMPLE_COMPOSITIONS.md`

```markdown
---
author: "Genesis"
generated_by: "Genesis"
---
# Example Compositions

## A. Research dashboard
`AppShell + ProjectHeader + ResearchStageBoard + EvidenceLedger + DocumentList + ReleaseChecklist + ActivityFeed`

## B. Agent orchestration
`AppShell + AgentRoster + WorkflowCanvas + TaskManifest + ExecutionTimeline + ApprovalGate + RetryResumePanel`

## C. Interactive model explorer
`AppShell + NetworkCanvas + NodeInspector + ScenarioWorkbench + BeforeAfterCompare + EvidenceLedger`

## D. Local application builder
`AppShell + FileExplorer + EditorShell + MainCanvas + RuntimeStatus + LogViewer + VersionDiff`

## E. Publishing workspace
`AppShell + ChapterNavigator + DocumentEditor + EditorialIssueList + VersionDiff + ReleaseChecklist`

## F. Multi-location service operations
`AppShell + KPIGrid + LocationComparison + OrderQueue + InventoryPanel + ExceptionQueue`

## G. Component library manager
`AppShell + LibraryImporter + ComponentPicker + ThemePicker + DesignTokenInspector + DependencyReport + VersionDiff`

These are composition specifications. They become functional only when connected to real host data, callbacks, permissions and runtime services.
```
