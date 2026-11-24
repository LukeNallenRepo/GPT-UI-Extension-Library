---
title: Application Library
type: ui-standard
updated: 2026-11-22
---

# Application Library

## Coverage rule
Every application, tool or substantial interactive workspace found in the Ecosystem Master receives a profile under `12_APP_PROFILES/`. A project folder is not automatically a shipped application: inventory entries distinguish `application`, `interactive workspace`, `knowledge system`, `planned product` and `supporting project`.

## Evidence labels
- `SOURCE-VERIFIED`: code, manifest or actual UI source inspected.
- `DOCUMENTED`: source documents describe the UI or workflow, but implementation was not confirmed.
- `INFERRED`: likely screens/components derived from an evidenced workflow.
- `PROPOSED`: recommended future design.
- `NOT INSPECTED`: relevant implementation not reviewed.

## Profile minimum
Each profile records: canonical project path, product purpose, audience/task, evidence/status, key journeys, screen inventory, navigation model, core components, visual identity, data states, responsive behaviour, accessibility, integration dependencies and open verification items.

## App discovery workflow
1. Inventory top-level projects and nested app source directories.
2. Inspect package manifests, entry points, route definitions, README/specs and UI source.
3. Distinguish app code from libraries, APIs, scripts, book/vault content and prototypes.
4. Map each actual app to a profile; map non-app projects to a workspace profile if they have meaningful interactive UI.
5. Record duplicate/legacy variants without treating them as separate products unless they have distinct user-facing purpose.
6. Re-run discovery when new app folders or manifests are added.

## Portfolio principle
The app library is a living catalogue. Never claim exhaustive coverage unless the directory scan and profile reconciliation have been completed against the current master archive.

