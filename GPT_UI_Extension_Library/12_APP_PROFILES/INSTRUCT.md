---
title: Application Profiles
type: ui-standard
updated: 2026-11-22
---

# Application Profiles

Profiles are stored as individual Markdown files in this directory. Each profile distinguishes source-verified implementation from documented workflows and proposed UI.

## Required profile fields
- Product and canonical path
- Product type and purpose
- Evidence/status label
- Primary users and jobs-to-be-done
- Core navigation and screens
- Key components and data visualisations
- Theme and brand identity
- Loading/empty/error/permission states
- Responsive and accessibility requirements
- Integration and data dependencies
- Open questions and verification actions

## Profile maintenance
Update a profile when the application source, user workflow, brand direction or architecture changes. Do not infer a deployment state from a folder existing. Keep legacy implementations and planned concepts clearly labelled.



## Theme and style mapping (mandatory)
For each profile, identify:
- selected generic theme preset(s),
- style components composed by the app,
- app-specific brand overrides,
- any accessibility or contrast exceptions.

Do not define a unique reusable theme solely for one app. A profile may record a brand accent or visual preference, but reusable themes belong in `01_DESIGN_SYSTEM/THEME_PRESETS/`. Reusable visual treatments belong in `02_COMPONENT_LIBRARY/STYLE_COMPONENTS/`.

Treat existing application profiles as worked examples. New unrelated apps should be able to reuse the same components without inheriting another app's name, logo, colour identity or domain-specific language.
