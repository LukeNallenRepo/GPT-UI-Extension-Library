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
