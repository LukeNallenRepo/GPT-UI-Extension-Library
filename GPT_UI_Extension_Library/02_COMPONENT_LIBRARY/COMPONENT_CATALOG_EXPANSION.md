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
