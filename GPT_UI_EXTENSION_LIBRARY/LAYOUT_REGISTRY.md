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
