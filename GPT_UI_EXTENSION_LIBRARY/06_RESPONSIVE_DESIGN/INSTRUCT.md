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

