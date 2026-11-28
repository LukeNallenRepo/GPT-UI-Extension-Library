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

