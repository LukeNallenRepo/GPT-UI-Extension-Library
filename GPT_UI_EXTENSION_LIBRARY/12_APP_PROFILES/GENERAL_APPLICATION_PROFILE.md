---
author: "Luke Nallen"
---

# General Application Profile

## Purpose
General-purpose SaaS, productivity tools, settings-driven products and multi-purpose applications.

## Primary user jobs
Orient users, expose primary tasks, show current context and provide predictable navigation.

## Suggested information architecture
Header, primary navigation, page title, contextual actions, overview cards, content region, settings and help.

## Reusable component families
- Navigation, breadcrumbs and contextual actions.
- Cards, lists, tables, tabs and responsive content grids.
- Search, filtering, sorting and forms where relevant.
- Status, progress, empty, loading, error and confirmation states.
- Accessible dialogs, menus, tooltips and notifications where supported.

## Theme options
Neutral Product; Light Product; High Contrast

Choose the theme independently according to the content, environment, user preference and contrast requirements. Do not bind this profile to a single preset.

## Data and integration boundary
The host application supplies all data, business rules, authentication, permissions, persistence, APIs and external integrations. This profile defines presentation only and has no mandatory resource or runtime dependency.

## Responsive and accessibility requirements
- Start with a narrow mobile layout; progressively enhance for tablet and desktop.
- Reflow sidebars and multi-column regions without hiding essential information.
- Provide semantic headings, labels, keyboard access, visible focus and sufficient contrast.
- Pair status colours with text or icons; do not rely on colour alone.
- Respect reduced-motion settings and provide non-animated alternatives.

## States to define
Specify realistic loading, empty, error, permission-denied, offline/stale, success and destructive-confirmation states as applicable. Do not claim a state exists unless the host supplies it.

## Customisation boundary
The host may supply its product name, logo, approved brand tokens, terminology and domain-specific content. Keep those overrides outside this generic profile and shared component definitions.

## Evidence status
DOCUMENTED — reusable composition guidance; not an executable application or implementation claim.
