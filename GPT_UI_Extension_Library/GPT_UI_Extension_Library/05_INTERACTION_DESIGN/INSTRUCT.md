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

