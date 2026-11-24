---
title: UI Extension Architecture and Import Map
version: 1.0.0
updated: 2026-11-23
status: integrated-library-specification
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
