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

