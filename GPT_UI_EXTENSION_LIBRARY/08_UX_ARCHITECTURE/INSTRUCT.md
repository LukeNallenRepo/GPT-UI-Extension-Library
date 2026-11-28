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

