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
