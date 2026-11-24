# GPT UI Extension Library — Consolidated ChatGPT Knowledge Bundle
> Generated from the canonical repository files for installation as one ChatGPT Project source or GPT Knowledge file. The repository files remain authoritative.


---

## SOURCE FILE: `01_DESIGN_SYSTEM/INSTRUCT.md`

```markdown
---
title: Design System
type: ui-standard
updated: 2026-11-22
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

## SOURCE FILE: `01_DESIGN_SYSTEM/THEME_PRESETS/INSTRUCT.md`

```markdown
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
title: Theme Registry
version: 1.0.0
updated: 2026-11-23
---

# Theme Registry

All themes are domain-neutral. Any component or application may use any preset.

| Theme ID | Intended use | Visual character | Reference alignment |
|---|---|---|---|
| `data-workbench` | Operations, analytics, technical dashboards | Deep navy/teal surfaces, cyan accent, restrained status colours | Operations Command Centre, Revenue Trend, Performance Overview |
| `neutral-product` | General-purpose SaaS and project tools | Dark neutral surfaces, blue-violet accent | Neutral Product |
| `creative-studio` | Audio, visual and creator tools | Deep violet surfaces, lavender and rose accents | Creative Studio, Genesis-style project workspace |
| `warm-editorial` | Reading, documentation and content | Warm off-white surfaces, earthy accent | Warm Editorial |
| `high-contrast` | Dense interfaces and accessibility-first views | Near-black surfaces, bright text and yellow/cyan accents | High Contrast |
| `light-product` | Bright productivity applications | White and cool-grey surfaces, blue accent | Light Product |

## Theme application rules

1. Select a theme by task and information density, not by application name.
2. Keep semantic status colours distinct from brand accent colours.
3. Apply app branding as a small token override; do not fork the preset.
4. Ensure all text, charts, controls and focus indicators remain legible.
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

## SOURCE FILE: `02_COMPONENT_LIBRARY/COMPONENT_CATALOG_EXPANSION.md`

```markdown
---
title: Expanded Universal Component Contracts
version: 1.0.0
updated: 2026-11-23
status: documented-component-specifications
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

## SOURCE FILE: `02_COMPONENT_LIBRARY/STYLE_COMPONENTS/INSTRUCT.md`

```markdown
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

## SOURCE FILE: `02_COMPONENT_LIBRARY/component_registry.json`

```json
{
  "version": "2.3.0",
  "updated": "2026-11-23",
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

## SOURCE FILE: `03_APP_LIBRARY/APP_INVENTORY.json`

```json
{
  "updated": "2026-11-23",
  "master_root": "CYBERSELF/ECOSYSTEM_MASTER",
  "profiles": [
    {
      "id": "ASCENSION_MASTER",
      "name": "Ascension Master / Ecosystem",
      "type": "knowledge system and portfolio workspace",
      "evidence": "DOCUMENTED",
      "path": "00_ASCENSION_MASTER/",
      "profile": "12_APP_PROFILES/ASCENSION_MASTER_UI_PROFILE.md"
    },
    {
      "id": "ECOSYSTEM_DASHBOARD",
      "name": "Ecosystem Dashboard",
      "type": "interactive operations workspace",
      "evidence": "SOURCE-VERIFIED (Markdown dashboard UI)",
      "path": "00_DASHBOARD/",
      "profile": "12_APP_PROFILES/ECOSYSTEM_DASHBOARD_UI_PROFILE.md"
    },
    {
      "id": "ASCENSION_CLOTHING",
      "name": "Ascension Clothing / Truth Project",
      "type": "brand and commerce project workspace",
      "evidence": "DOCUMENTED",
      "path": "02_APPAREL/",
      "profile": "12_APP_PROFILES/ASCENSION_CLOTHING_UI_PROFILE.md"
    },
    {
      "id": "BUSINESS_LAYER",
      "name": "Business Layer",
      "type": "planned business workspace",
      "evidence": "DOCUMENTED",
      "path": "04_BUSINESS/",
      "profile": "12_APP_PROFILES/BUSINESS_LAYER_UI_PROFILE.md"
    },
    {
      "id": "OPERATIONS",
      "name": "Ecosystem Operations",
      "type": "operations and governance workspace",
      "evidence": "DOCUMENTED",
      "path": "05_OPERATIONS/",
      "profile": "12_APP_PROFILES/OPERATIONS_UI_PROFILE.md"
    },
    {
      "id": "MARKET_MASTER",
      "name": "Market Master OS",
      "type": "market research and portfolio-analysis system",
      "evidence": "SOURCE-VERIFIED (project structure and source documents)",
      "path": "12_Market_Master/",
      "profile": "12_APP_PROFILES/MARKET_MASTER_UI_PROFILE.md"
    },
    {
      "id": "GPT_CLI_TOOLS",
      "name": "GPT CLI Tools",
      "type": "developer tooling and prompt/workflow toolkit",
      "evidence": "DOCUMENTED",
      "path": "14_GPT_CLI_TOOLS/",
      "profile": "12_APP_PROFILES/GPT_CLI_TOOLS_UI_PROFILE.md"
    },
    {
      "id": "ECOSYSTEM_MASTER_CREATOR",
      "name": "Ecosystem Master Creator",
      "type": "knowledge-base creation and repair workspace",
      "evidence": "DOCUMENTED",
      "path": "16_Ecosystem_master_creator_RM/",
      "profile": "12_APP_PROFILES/ECOSYSTEM_MASTER_CREATOR_UI_PROFILE.md"
    },
    {
      "id": "LOCALFORGE",
      "name": "LocalForge",
      "type": "web-based code workspace / app builder",
      "evidence": "SOURCE-VERIFIED (package manifest and React/Vite entry points)",
      "path": "17_LocalForge/",
      "profile": "12_APP_PROFILES/LOCALFORGE_UI_PROFILE.md"
    },
    {
      "id": "GENESIS_FORGE",
      "name": "Genesis / Genesis Forge",
      "type": "agent, skill and project creation system",
      "evidence": "DOCUMENTED",
      "path": "19_Genesis/",
      "profile": "12_APP_PROFILES/GENESIS_FORGE_UI_PROFILE.md"
    },
    {
      "id": "QUESTMASTER",
      "name": "Questmaster",
      "type": "task orchestration and operations command centre",
      "evidence": "SOURCE-VERIFIED (dashboard Markdown and UI instructions)",
      "path": "20_Questmaster/",
      "profile": "12_APP_PROFILES/QUESTMASTER_UI_PROFILE.md"
    },
    {
      "id": "QUESTMASTER_V1",
      "name": "Questmaster V1 Legacy",
      "type": "legacy task-management workspace",
      "evidence": "DOCUMENTED",
      "path": "23_QM_V1 (complete, testing)/",
      "profile": "12_APP_PROFILES/QUESTMASTER_V1_UI_PROFILE.md"
    },
    {
      "id": "WARDEN",
      "name": "Warden",
      "type": "file intake and canonical resource management",
      "evidence": "DOCUMENTED / WORKFLOW-DERIVED",
      "path": "24_Warden (file handling in and out of a.i)/",
      "profile": "12_APP_PROFILES/WARDEN_UI_PROFILE.md"
    },
    {
      "id": "ETHINDEX",
      "name": "EthIndex",
      "type": "proposed Ethereum ecosystem index product",
      "evidence": "DOCUMENTED (concept/whitepaper; implementation unknown)",
      "path": "25_EthIndex/",
      "profile": "12_APP_PROFILES/ETHINDEX_UI_PROFILE.md"
    },
    {
      "id": "DTT_GPT_APP",
      "name": "DTT GPT App",
      "type": "Irish Driver Theory Test learning application",
      "evidence": "SOURCE-VERIFIED (instruction and formatting specifications)",
      "path": "DTT_GPT_APP/",
      "profile": "12_APP_PROFILES/DTT_GPT_APP_UI_PROFILE.md"
    },
    {
      "id": "ELEV8",
      "name": "Elev8",
      "type": "supporting project / workspace",
      "evidence": "DOCUMENTED (project files; app status unknown)",
      "path": "Elev8/",
      "profile": "12_APP_PROFILES/ELEV8_UI_PROFILE.md"
    },
    {
      "id": "LIFEPLANS",
      "name": "Lifeplans",
      "type": "personal planning knowledge workspace",
      "evidence": "DOCUMENTED (project files; app status unknown)",
      "path": "Lifeplans/",
      "profile": "12_APP_PROFILES/LIFEPLANS_UI_PROFILE.md"
    },
    {
      "id": "KARMA_CIRCLE_WEB",
      "name": "The Karma Circle UI",
      "type": "web application / interactive framework",
      "evidence": "SOURCE-VERIFIED (nested package manifest and React/Vite app artifact)",
      "path": "00_ASCENSION_MASTER/09_THE_KARMA_CIRCLE/Kc1/TheKarmaCircleUi/artifacts/artifacts/karma-circle/",
      "profile": "12_APP_PROFILES/KARMA_CIRCLE_WEB_UI_PROFILE.md"
    },
    {
      "id": "KARMA_CIRCLE_MOCKUP",
      "name": "Karma Circle Mockup Sandbox",
      "type": "prototype and visual exploration",
      "evidence": "SOURCE-VERIFIED (nested package manifest)",
      "path": "00_ASCENSION_MASTER/09_THE_KARMA_CIRCLE/Kc1/TheKarmaCircleUi/artifacts/artifacts/mockup-sandbox/",
      "profile": "12_APP_PROFILES/KARMA_CIRCLE_MOCKUP_UI_PROFILE.md"
    }
  ],
  "notes": [
    "Coverage is based on inspection of the mounted 22 November 2026 archive.",
    "Nested Karma Circle workspace includes a React/Vite app artifact and a mockup sandbox; package manifests were inspected.",
    "LocalForge has a package manifest and React/Vite entry points; the profile is source-verified for project architecture.",
    "Questmaster dashboard Markdown and UI instructions were inspected; its documented interface is source-backed, but live runtime is not implied.",
    "Other profile evidence is documentary unless stated otherwise.",
    "Supporting libraries, API packages, scripts, knowledge vaults and books are not counted as separate user-facing applications unless they expose a distinct UI."
  ],
  "public_release_privacy_note": "Personal health-record application profiles are excluded from this public repository."
}
```


---

## SOURCE FILE: `03_APP_LIBRARY/APP_INVENTORY.md`

```markdown
# Ecosystem Application Inventory

Updated: 23 November 2026

| Application / workspace | Type | Evidence | Canonical path | Profile |
|---|---|---|---|---|
| Ascension Master / Ecosystem | knowledge system and portfolio workspace | DOCUMENTED | `00_ASCENSION_MASTER/` | [`ASCENSION_MASTER_UI_PROFILE.md`](12_APP_PROFILES/ASCENSION_MASTER_UI_PROFILE.md) |
| Ecosystem Dashboard | interactive operations workspace | SOURCE-VERIFIED (Markdown dashboard UI) | `00_DASHBOARD/` | [`ECOSYSTEM_DASHBOARD_UI_PROFILE.md`](12_APP_PROFILES/ECOSYSTEM_DASHBOARD_UI_PROFILE.md) |
| Ascension Clothing / Truth Project | brand and commerce project workspace | DOCUMENTED | `02_APPAREL/` | [`ASCENSION_CLOTHING_UI_PROFILE.md`](12_APP_PROFILES/ASCENSION_CLOTHING_UI_PROFILE.md) |
| Business Layer | planned business workspace | DOCUMENTED | `04_BUSINESS/` | [`BUSINESS_LAYER_UI_PROFILE.md`](12_APP_PROFILES/BUSINESS_LAYER_UI_PROFILE.md) |
| Ecosystem Operations | operations and governance workspace | DOCUMENTED | `05_OPERATIONS/` | [`OPERATIONS_UI_PROFILE.md`](12_APP_PROFILES/OPERATIONS_UI_PROFILE.md) |
| Market Master OS | market research and portfolio-analysis system | SOURCE-VERIFIED (project structure and source documents) | `12_Market_Master/` | [`MARKET_MASTER_UI_PROFILE.md`](12_APP_PROFILES/MARKET_MASTER_UI_PROFILE.md) |
| GPT CLI Tools | developer tooling and prompt/workflow toolkit | DOCUMENTED | `14_GPT_CLI_TOOLS/` | [`GPT_CLI_TOOLS_UI_PROFILE.md`](12_APP_PROFILES/GPT_CLI_TOOLS_UI_PROFILE.md) |
| Ecosystem Master Creator | knowledge-base creation and repair workspace | DOCUMENTED | `16_Ecosystem_master_creator_RM/` | [`ECOSYSTEM_MASTER_CREATOR_UI_PROFILE.md`](12_APP_PROFILES/ECOSYSTEM_MASTER_CREATOR_UI_PROFILE.md) |
| LocalForge | web-based code workspace / app builder | SOURCE-VERIFIED (package manifest and React/Vite entry points) | `17_LocalForge/` | [`LOCALFORGE_UI_PROFILE.md`](12_APP_PROFILES/LOCALFORGE_UI_PROFILE.md) |
| Genesis / Genesis Forge | agent, skill and project creation system | DOCUMENTED | `19_Genesis/` | [`GENESIS_FORGE_UI_PROFILE.md`](12_APP_PROFILES/GENESIS_FORGE_UI_PROFILE.md) |
| Questmaster | task orchestration and operations command centre | SOURCE-VERIFIED (dashboard Markdown and UI instructions) | `20_Questmaster/` | [`QUESTMASTER_UI_PROFILE.md`](12_APP_PROFILES/QUESTMASTER_UI_PROFILE.md) |
| Questmaster V1 Legacy | legacy task-management workspace | DOCUMENTED | `23_QM_V1 (complete, testing)/` | [`QUESTMASTER_V1_UI_PROFILE.md`](12_APP_PROFILES/QUESTMASTER_V1_UI_PROFILE.md) |
| Warden | file intake and canonical resource management | DOCUMENTED / WORKFLOW-DERIVED | `24_Warden (file handling in and out of a.i)/` | [`WARDEN_UI_PROFILE.md`](12_APP_PROFILES/WARDEN_UI_PROFILE.md) |
| EthIndex | proposed Ethereum ecosystem index product | DOCUMENTED (concept/whitepaper; implementation unknown) | `25_EthIndex/` | [`ETHINDEX_UI_PROFILE.md`](12_APP_PROFILES/ETHINDEX_UI_PROFILE.md) |
| DTT GPT App | Irish Driver Theory Test learning application | SOURCE-VERIFIED (instruction and formatting specifications) | `DTT_GPT_APP/` | [`DTT_GPT_APP_UI_PROFILE.md`](12_APP_PROFILES/DTT_GPT_APP_UI_PROFILE.md) |
| Elev8 | supporting project / workspace | DOCUMENTED (project files; app status unknown) | `Elev8/` | [`ELEV8_UI_PROFILE.md`](12_APP_PROFILES/ELEV8_UI_PROFILE.md) |
| Lifeplans | personal planning knowledge workspace | DOCUMENTED (project files; app status unknown) | `Lifeplans/` | [`LIFEPLANS_UI_PROFILE.md`](12_APP_PROFILES/LIFEPLANS_UI_PROFILE.md) |
| The Karma Circle UI | web application / interactive framework | SOURCE-VERIFIED (nested package manifest and React/Vite app artifact) | `00_ASCENSION_MASTER/09_THE_KARMA_CIRCLE/Kc1/TheKarmaCircleUi/artifacts/artifacts/karma-circle/` | [`KARMA_CIRCLE_WEB_UI_PROFILE.md`](12_APP_PROFILES/KARMA_CIRCLE_WEB_UI_PROFILE.md) |
| Karma Circle Mockup Sandbox | prototype and visual exploration | SOURCE-VERIFIED (nested package manifest) | `00_ASCENSION_MASTER/09_THE_KARMA_CIRCLE/Kc1/TheKarmaCircleUi/artifacts/artifacts/mockup-sandbox/` | [`KARMA_CIRCLE_MOCKUP_UI_PROFILE.md`](12_APP_PROFILES/KARMA_CIRCLE_MOCKUP_UI_PROFILE.md) |

## Coverage notes

- Coverage is based on inspection of the mounted 22 November 2026 archive.
- Nested Karma Circle workspace includes a React/Vite app artifact and a mockup sandbox; package manifests were inspected.
- LocalForge has a package manifest and React/Vite entry points; the profile is source-verified for project architecture.
- Questmaster dashboard Markdown and UI instructions were inspected; its documented interface is source-backed, but live runtime is not implied.
- Other profile evidence is documentary unless stated otherwise.
- Supporting libraries, API packages, scripts, knowledge vaults and books are not counted as separate user-facing applications unless they expose a distinct UI.

> Privacy note: personal health-record application profiles are excluded from this public repository. Add such profiles only in a private application-specific workspace.
```


---

## SOURCE FILE: `03_APP_LIBRARY/INSTRUCT.md`

```markdown
---
title: Application Library
type: ui-standard
updated: 2026-11-22
---

# Application Library

## Coverage rule
Every application, tool or substantial interactive workspace found in the Ecosystem Master receives a profile under `12_APP_PROFILES/`. A project folder is not automatically a shipped application: inventory entries distinguish `application`, `interactive workspace`, `knowledge system`, `planned product` and `supporting project`.

## Evidence labels
- `SOURCE-VERIFIED`: code, manifest or actual UI source inspected.
- `DOCUMENTED`: source documents describe the UI or workflow, but implementation was not confirmed.
- `INFERRED`: likely screens/components derived from an evidenced workflow.
- `PROPOSED`: recommended future design.
- `NOT INSPECTED`: relevant implementation not reviewed.

## Profile minimum
Each profile records: canonical project path, product purpose, audience/task, evidence/status, key journeys, screen inventory, navigation model, core components, visual identity, data states, responsive behaviour, accessibility, integration dependencies and open verification items.

## App discovery workflow
1. Inventory top-level projects and nested app source directories.
2. Inspect package manifests, entry points, route definitions, README/specs and UI source.
3. Distinguish app code from libraries, APIs, scripts, book/vault content and prototypes.
4. Map each actual app to a profile; map non-app projects to a workspace profile if they have meaningful interactive UI.
5. Record duplicate/legacy variants without treating them as separate products unless they have distinct user-facing purpose.
6. Re-run discovery when new app folders or manifests are added.

## Portfolio principle
The app library is a living catalogue. Never claim exhaustive coverage unless the directory scan and profile reconciliation have been completed against the current master archive.
```


---

## SOURCE FILE: `04_DASHBOARD_DESIGN/INSTRUCT.md`

```markdown
---
title: Dashboard Design
type: ui-standard
updated: 2026-11-22
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

## SOURCE FILE: `12_APP_PROFILES/ASCENSION_CLOTHING_UI_PROFILE.md`

```markdown
---
title: "Ascension Clothing / Truth Project UI Profile"
application: "ASCENSION_CLOTHING"
project_path: "02_APPAREL/"
product_type: "brand and commerce project workspace"
evidence_status: "DOCUMENTED"
updated: "2026-11-22"
---

# Ascension Clothing / Truth Project — UI Profile

## Product type and purpose
brand and commerce project workspace. Manage collections, brand identity, customer, marketing and launch readiness.

## Evidence status
**DOCUMENTED.** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Brand home; collection index; collection detail; asset library; marketing calendar; governance.

## Visual identity and layout
Minimalist, symbolic and memetic; preserve approved logos and collection identity; premium editorial presentation.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/ASCENSION_MASTER_UI_PROFILE.md`

```markdown
---
title: "Ascension Master / Ecosystem UI Profile"
application: "ASCENSION_MASTER"
project_path: "00_ASCENSION_MASTER/"
product_type: "knowledge system and portfolio workspace"
evidence_status: "DOCUMENTED"
updated: "2026-11-22"
---

# Ascension Master / Ecosystem — UI Profile

## Product type and purpose
knowledge system and portfolio workspace. Portfolio navigation across Ascension, research, Karma Circle, Behaviour OS, Lucifer's Language and THE GAME.

## Evidence status
**DOCUMENTED.** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
A calm, high-level ecosystem overview; project index; research and governance navigation; project status and integration views.

## Visual identity and layout
Cosmic/geometric identity with restrained violet/cyan accents; prioritise legibility over decorative effects.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/BUSINESS_LAYER_UI_PROFILE.md`

```markdown
---
title: "Business Layer UI Profile"
application: "BUSINESS_LAYER"
project_path: "04_BUSINESS/"
product_type: "planned business workspace"
evidence_status: "DOCUMENTED"
updated: "2026-11-22"
---

# Business Layer — UI Profile

## Product type and purpose
planned business workspace. Coordinate business model, commercial dependencies and operating decisions.

## Evidence status
**DOCUMENTED.** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Business overview; model canvas; finance/operations links; decisions and milestones.

## Visual identity and layout
Professional, restrained business interface; clearly label planned content and unknown metrics.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/DTT_GPT_APP_UI_PROFILE.md`

```markdown
---
title: "DTT GPT App UI Profile"
application: "DTT_GPT_APP"
project_path: "DTT_GPT_APP/"
product_type: "Irish Driver Theory Test learning application"
evidence_status: "SOURCE-VERIFIED (instruction and formatting specifications)"
updated: "2026-11-22"
---

# DTT GPT App — UI Profile

## Product type and purpose
Irish Driver Theory Test learning application. Deliver one-question-at-a-time practice grounded in the official question bank.

## Evidence status
**SOURCE-VERIFIED (instruction and formatting specifications).** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Question screen; official source/image display; keyword chain; scenario; selectable answers; submit; explanation/review.

## Visual identity and layout
Focused learning UI; large readable question text; authentic source image only; no answer reveal before submission.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/ECOSYSTEM_DASHBOARD_UI_PROFILE.md`

```markdown
---
title: "Ecosystem Dashboard UI Profile"
application: "ECOSYSTEM_DASHBOARD"
project_path: "00_DASHBOARD/"
product_type: "interactive operations workspace"
evidence_status: "SOURCE-VERIFIED (Markdown dashboard UI)"
updated: "2026-11-22"
---

# Ecosystem Dashboard — UI Profile

## Product type and purpose
interactive operations workspace. Orient the user to portfolio health, active projects, operations, tasks and agent status.

## Evidence status
**SOURCE-VERIFIED (Markdown dashboard UI).** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Home dashboard; project status; weekly integrations; registry; agent system integration.

## Visual identity and layout
Dark operational dashboard, strong hierarchy, compact status summaries; snapshot/live distinction must be explicit.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/ECOSYSTEM_MASTER_CREATOR_UI_PROFILE.md`

```markdown
---
title: "Ecosystem Master Creator UI Profile"
application: "ECOSYSTEM_MASTER_CREATOR"
project_path: "16_Ecosystem_master_creator_RM/"
product_type: "knowledge-base creation and repair workspace"
evidence_status: "DOCUMENTED"
updated: "2026-11-22"
---

# Ecosystem Master Creator — UI Profile

## Product type and purpose
knowledge-base creation and repair workspace. Create, inspect, consolidate and repair ecosystem master structures.

## Evidence status
**DOCUMENTED.** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Creator home; readiness; source intake; build plan; validation; repair queue; run history.

## Visual identity and layout
File-centric workspace with provenance, preview-before-write, diff and recoverability.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/ELEV8_UI_PROFILE.md`

```markdown
---
title: "Elev8 UI Profile"
application: "ELEV8"
project_path: "Elev8/"
product_type: "supporting project / workspace"
evidence_status: "DOCUMENTED (project files; app status unknown)"
updated: "2026-11-22"
---

# Elev8 — UI Profile

## Product type and purpose
supporting project / workspace. Organise Elev8 project notes and related C-liquid material.

## Evidence status
**DOCUMENTED (project files; app status unknown).** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Project home; notes; C-liquid knowledge pages; references.

## Visual identity and layout
Use a clear knowledge-workspace layout; do not invent interactive features absent from source.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/ETHINDEX_UI_PROFILE.md`

```markdown
---
title: "EthIndex UI Profile"
application: "ETHINDEX"
project_path: "25_EthIndex/"
product_type: "proposed Ethereum ecosystem index product"
evidence_status: "DOCUMENTED (concept/whitepaper; implementation unknown)"
updated: "2026-11-22"
---

# EthIndex — UI Profile

## Product type and purpose
proposed Ethereum ecosystem index product. Explain index composition, deposits, token representation, redemption and portfolio transparency.

## Evidence status
**DOCUMENTED (concept/whitepaper; implementation unknown).** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Product overview; holdings/composition; token balance; transaction history; deposit/redeem flows (only if implemented); risk and contract details.

## Visual identity and layout
Trust-first financial UI; transparent fees, risks, contract addresses and transaction states; no fabricated live balances.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/GENESIS_FORGE_UI_PROFILE.md`

```markdown
---
title: "Genesis / Genesis Forge UI Profile"
application: "GENESIS_FORGE"
project_path: "19_Genesis/"
product_type: "agent, skill and project creation system"
evidence_status: "DOCUMENTED"
updated: "2026-11-22"
---

# Genesis / Genesis Forge — UI Profile

## Product type and purpose
agent, skill and project creation system. Create projects, agents, skills and supporting resources from structured natural-language requests.

## Evidence status
**DOCUMENTED.** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Command entry; creation wizard; prompt-engineering review; generated artifact preview; registry; validation.

## Visual identity and layout
Creation-first interface; guided steps, transparent generated content, clear provenance and validation feedback.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/GPT_CLI_TOOLS_UI_PROFILE.md`

```markdown
---
title: "GPT CLI Tools UI Profile"
application: "GPT_CLI_TOOLS"
project_path: "14_GPT_CLI_TOOLS/"
product_type: "developer tooling and prompt/workflow toolkit"
evidence_status: "DOCUMENTED"
updated: "2026-11-22"
---

# GPT CLI Tools — UI Profile

## Product type and purpose
developer tooling and prompt/workflow toolkit. Create and manage agents and related CLI-driven ecosystem assets.

## Evidence status
**DOCUMENTED.** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Command reference; creation workflows; output preview; validation and logs.

## Visual identity and layout
Developer-tool clarity; monospace for commands only; copyable examples and explicit operation results.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/INSTRUCT.md`

```markdown
---
title: Application Profiles
type: ui-standard
updated: 2026-11-22
---

# Application Profiles

Profiles are stored as individual Markdown files in this directory. Each profile distinguishes source-verified implementation from documented workflows and proposed UI.

## Required profile fields
- Product and canonical path
- Product type and purpose
- Evidence/status label
- Primary users and jobs-to-be-done
- Core navigation and screens
- Key components and data visualisations
- Theme and brand identity
- Loading/empty/error/permission states
- Responsive and accessibility requirements
- Integration and data dependencies
- Open questions and verification actions

## Profile maintenance
Update a profile when the application source, user workflow, brand direction or architecture changes. Do not infer a deployment state from a folder existing. Keep legacy implementations and planned concepts clearly labelled.



## Theme and style mapping (mandatory)
For each profile, identify:
- selected generic theme preset(s),
- style components composed by the app,
- app-specific brand overrides,
- any accessibility or contrast exceptions.

Do not define a unique reusable theme solely for one app. A profile may record a brand accent or visual preference, but reusable themes belong in `01_DESIGN_SYSTEM/THEME_PRESETS/`. Reusable visual treatments belong in `02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`.

Treat existing application profiles as worked examples. New unrelated apps should be able to reuse the same components without inheriting another app's name, logo, colour identity or domain-specific language.
```


---

## SOURCE FILE: `12_APP_PROFILES/KARMA_CIRCLE_MOCKUP_UI_PROFILE.md`

```markdown
---
title: "Karma Circle Mockup Sandbox UI Profile"
application: "KARMA_CIRCLE_MOCKUP"
project_path: "00_ASCENSION_MASTER/09_THE_KARMA_CIRCLE/Kc1/TheKarmaCircleUi/artifacts/artifacts/mockup-sandbox/"
product_type: "prototype and visual exploration"
evidence_status: "SOURCE-VERIFIED (nested package manifest)"
updated: "2026-11-22"
---

# Karma Circle Mockup Sandbox — UI Profile

## Product type and purpose
prototype and visual exploration. Explore interface prototypes and test visual patterns separately from the production app.

## Evidence status
**SOURCE-VERIFIED (nested package manifest).** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Mockup canvas; component examples; prototype navigation; comparison views.

## Visual identity and layout
Clearly mark mock data and prototype-only behaviour; promote to product only after review.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/KARMA_CIRCLE_WEB_UI_PROFILE.md`

```markdown
---
title: "The Karma Circle UI UI Profile"
application: "KARMA_CIRCLE_WEB"
project_path: "00_ASCENSION_MASTER/09_THE_KARMA_CIRCLE/Kc1/TheKarmaCircleUi/artifacts/artifacts/karma-circle/"
product_type: "web application / interactive framework"
evidence_status: "SOURCE-VERIFIED (nested package manifest and React/Vite app artifact)"
updated: "2026-11-22"
---

# The Karma Circle UI — UI Profile

## Product type and purpose
web application / interactive framework. Present the Karma Circle framework, simulator and related interactive experiences.

## Evidence status
**SOURCE-VERIFIED (nested package manifest and React/Vite app artifact).** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Application shell; framework cards; 18-node model visualiser; simulation/scenario controls; resonance/dissonance indicators; trajectory and insight panels; interventions; quests and reflection.

## Visual identity and layout
Distinctive cyan/magenta/red identity; make model states interpretable; label simulation outputs and confidence; avoid presenting conceptual scores as clinical facts.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/LIFEPLANS_UI_PROFILE.md`

```markdown
---
title: "Lifeplans UI Profile"
application: "LIFEPLANS"
project_path: "Lifeplans/"
product_type: "personal planning knowledge workspace"
evidence_status: "DOCUMENTED (project files; app status unknown)"
updated: "2026-11-22"
---

# Lifeplans — UI Profile

## Product type and purpose
personal planning knowledge workspace. Organise plans across income, housing, fitness, transport, health and extra income.

## Evidence status
**DOCUMENTED (project files; app status unknown).** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Plan overview; domain navigation; plan detail; milestones and status.

## Visual identity and layout
Calm, low-friction planning UI; privacy-conscious presentation and clear separation of plans from verified outcomes.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/LOCALFORGE_UI_PROFILE.md`

```markdown
---
title: "LocalForge UI Profile"
application: "LOCALFORGE"
project_path: "17_LocalForge/"
product_type: "web-based code workspace / app builder"
evidence_status: "SOURCE-VERIFIED (package manifest and React/Vite entry points)"
updated: "2026-11-22"
---

# LocalForge — UI Profile

## Product type and purpose
web-based code workspace / app builder. Edit project files, run commands, inspect status and preview applications.

## Evidence status
**SOURCE-VERIFIED (package manifest and React/Vite entry points).** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
File explorer; editor; terminal; run/stop controls; preview; backend/API status; output/log panel.

## Visual identity and layout
Professional developer IDE; compact dark workspace, resizable panes, clear runtime state and safe destructive file operations.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/MARKET_MASTER_UI_PROFILE.md`

```markdown
---
title: "Market Master OS UI Profile"
application: "MARKET_MASTER"
project_path: "12_Market_Master/"
product_type: "market research and portfolio-analysis system"
evidence_status: "SOURCE-VERIFIED (project structure and source documents)"
updated: "2026-11-22"
---

# Market Master OS — UI Profile

## Product type and purpose
market research and portfolio-analysis system. Research market regimes, indicators, portfolio logic, risk models and validation.

## Evidence status
**SOURCE-VERIFIED (project structure and source documents).** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Market overview; indicator library; research lab; dataset audit; portfolio/risk views; validation workspace.

## Visual identity and layout
Data-dense analyst workstation; precise chart labels, timeframe controls, provenance and explicit research-vs-live boundaries.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/OPERATIONS_UI_PROFILE.md`

```markdown
---
title: "Ecosystem Operations UI Profile"
application: "OPERATIONS"
project_path: "05_OPERATIONS/"
product_type: "operations and governance workspace"
evidence_status: "DOCUMENTED"
updated: "2026-11-22"
---

# Ecosystem Operations — UI Profile

## Product type and purpose
operations and governance workspace. Manage tasks, workflows, roadmap, routing, approvals and runtime readiness.

## Evidence status
**DOCUMENTED.** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Operations overview; task list; roadmap; workflow; agent routing; runtime status; backlog.

## Visual identity and layout
High information clarity; risk/status cues; approval and audit history; never imply autonomous execution without evidence.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/QUESTMASTER_UI_PROFILE.md`

```markdown
---
title: "Questmaster UI Profile"
application: "QUESTMASTER"
project_path: "20_Questmaster/"
product_type: "task orchestration and operations command centre"
evidence_status: "SOURCE-VERIFIED (dashboard Markdown and UI instructions)"
updated: "2026-11-22"
---

# Questmaster — UI Profile

## Product type and purpose
task orchestration and operations command centre. Intake, prioritise, plan and track tasks through canonical records and weekly manifests.

## Evidence status
**SOURCE-VERIFIED (dashboard Markdown and UI instructions).** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Command centre; task dashboard; weekly operations; task ledger; task detail; agent assignment (planned); execution/handoff records.

## Visual identity and layout
Dark operations shell; violet/cyan accents; ledger-first data integrity; priority and lifecycle states prominent.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/QUESTMASTER_V1_UI_PROFILE.md`

```markdown
---
title: "Questmaster V1 Legacy UI Profile"
application: "QUESTMASTER_V1"
project_path: "23_QM_V1 (complete, testing)/"
product_type: "legacy task-management workspace"
evidence_status: "DOCUMENTED"
updated: "2026-11-22"
---

# Questmaster V1 Legacy — UI Profile

## Product type and purpose
legacy task-management workspace. Retain and inspect the earlier complete/testing version for comparison and migration.

## Evidence status
**DOCUMENTED.** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Legacy dashboard; task views; workflow views; migration comparison.

## Visual identity and layout
Treat as legacy/compatibility profile; do not visually merge into current Questmaster without an explicit migration decision.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `12_APP_PROFILES/WARDEN_UI_PROFILE.md`

```markdown
---
title: "Warden UI Profile"
application: "WARDEN"
project_path: "24_Warden (file handling in and out of a.i)/"
product_type: "file intake and canonical resource management"
evidence_status: "DOCUMENTED / WORKFLOW-DERIVED"
updated: "2026-11-22"
---

# Warden — UI Profile

## Product type and purpose
file intake and canonical resource management. Receive resources, identify type/project, validate metadata, preview names and route to canonical destinations.

## Evidence status
**DOCUMENTED / WORKFLOW-DERIVED.** This label describes the inspected source basis, not deployment readiness. Screens inferred from workflows remain proposals until code is inspected.

## Primary user journey
1. Enter the application and understand the current workspace/context.
2. Navigate to the primary task.
3. Review relevant information, constraints and current state.
4. Perform the task with clear progress and feedback.
5. Inspect the result, source/provenance and next action.

## Screen inventory
Intake queue; metadata inspector; naming preview; duplicate/conflict review; destination selector; audit report.

## Visual identity and layout
Precise file-management interface; preview and approval before writes; strong provenance and version visibility.

## Required interaction states
- Initial/loading state with layout-preserving skeletons where appropriate.
- Empty state with explanation and a relevant next action.
- Success state with result and traceable confirmation.
- Error state with actionable recovery and preserved user input where safe.
- Permission/approval state where operations require human authorisation.
- Offline/stale state wherever data freshness matters.

## Responsive guidance
- Desktop: optimise the primary workflow and contextual detail.
- Tablet: collapse secondary navigation and inspectors.
- Mobile: prioritise the main task; move secondary panels into drawers or stacked sections.
- Ensure tables, graphs, editors and source previews have intentional mobile behaviour.

## Accessibility
Use semantic headings, labelled controls, keyboard navigation, visible focus, non-colour status indicators and text alternatives for charts/diagrams. Respect reduced-motion preferences.

## Reusable components
Use shared AppShell, navigation, cards, forms, status badges, data tables, empty/error states and notification patterns. Add domain-specific components only where the workflow requires them.

## Verification and open questions
- Verify exact routes, screens, component APIs and data contracts against current source.
- Verify whether the UI is deployed, prototype-only or documentation-only.
- Record real runtime status separately from documented workflow.
- Do not fabricate live data, agent activity, model validity or financial balances.

## Shared theme/component mapping
This profile is an application-specific example, not a reusable theme definition. Rebuild its visual language by selecting one or more generic presets from `../01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`, composing reusable style components from `../02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`, then applying only the app's approved brand overrides. Do not fork shared components or require this app's palette for another product.
```


---

## SOURCE FILE: `APP_BUILDER_INSTRUCT.md`

```markdown
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
```


---

## SOURCE FILE: `INSTRUCT.md`

```markdown
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
```


---

## SOURCE FILE: `LAYOUT_REGISTRY.md`

```markdown
---
title: Universal Layout Registry
version: 1.0.0
updated: 2026-11-23
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
```


---

## SOURCE FILE: `MOUNT_INSTRUCT.md`

```markdown
---
title: Mount and Resume Instructions
version: 1.0.0
updated: 2026-11-23
status: portable-operating-instruction
---

# Mount and Resume Instructions

## Purpose

Make this library usable in a separate ChatGPT account, custom GPT, project workspace or external AI runtime without relying on the original account's memory or conversation history.

## Import procedure

1. Upload or attach the complete `15_GPT_UI_extension_library` folder/archive to the destination workspace.
2. Ensure the folder is available to the assistant as a knowledge source. If the host cannot index folders, retain the archive and provide the relevant registry and instruction files as separate sources.
3. Start a conversation with: `Mount UI extension library`.
4. The assistant should locate and read, in order:
   - `INSTRUCT.md`
   - `MOUNT_INSTRUCT.md`
   - `UI_EXTENSION_ARCHITECTURE.md`
   - `UNIVERSAL_COMPONENT_REGISTRY.md`
   - `02_COMPONENT_LIBRARY/component_registry.json`
   - `01_DESIGN_SYSTEM/THEME_PRESETS/theme_presets.json`
   - `LAYOUT_REGISTRY.md`
   - `APP_BUILDER_INSTRUCT.md`
   - `09_IMPLEMENTATION/CHATGPT_VISUAL_ADAPTER.md`
5. Confirm the discovered library version, component count, theme count, available adapters and any missing files.
6. Treat the uploaded files as the portable source of truth. Do not assume access to another account's files, memory, projects or connected apps.

## Mount response contract

After mounting, report:

- Library version and update date, including the architecture specification version.
- Number of registered component families and components.
- Available themes and layout patterns.
- Available render adapters and known limitations.
- Whether source files are fully accessible or only partially indexed.
- Any registry/file inconsistencies.

Do not claim that a live software package has been installed merely because documentation has been uploaded. A mount makes the specifications and instructions available to the assistant; executable React components still need to be implemented or installed in the target runtime.

## Resume protocol

When a later chat says `resume UI library`, `use mounted UI library` or asks to build an app:

1. Re-read the registry and relevant component contracts if the current conversation does not contain them.
2. Identify the requested app's purpose, data sources and interactions.
3. Reuse existing components and themes before proposing new ones.
4. Record any newly created component in both registries.
5. Keep app-specific configuration separate from the shared library.
6. Return a visual interface whenever the host supports it; otherwise use the documented fallback.

## Cross-account portability boundary

The archive is self-contained documentation and design specification. It does not transfer account memory, connector authorisations, private files, credentials, deployed code or runtime permissions. Each destination account must be granted access to the archive and independently connect any required services. The assistant must disclose these limits rather than imply automatic cross-account synchronisation.
```


---

## SOURCE FILE: `Notes/Marketing.md`

```markdown
giving AI assistants a reusable visual and architectural vocabulary for building applications.
```


---

## SOURCE FILE: `UI_EXTENSION_ARCHITECTURE.md`

```markdown
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
```


---

## SOURCE FILE: `UNIVERSAL_COMPONENT_REGISTRY.md`

```markdown
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
