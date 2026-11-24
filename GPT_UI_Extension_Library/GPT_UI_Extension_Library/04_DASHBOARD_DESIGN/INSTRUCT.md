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
