---
author: "Luke Nallen"
---

# Reusable Style Components — AI Instructions

## Purpose
Turn visual treatments into composable, reusable style components. Components must be independent of any one app's brand, domain or information architecture.

## Component catalogue

| Component | Purpose | Configurable properties |
|---|---|---|
| `Surface` | Base content surface | tone, elevation, radius, border |
| `GlassSurface` | Translucent layered surface | opacity, blur, tint, border, fallback |
| `GradientSurface` | Restrained gradient emphasis | start/end tokens, direction, intensity |
| `GlowAccent` | Focus or selected-state emphasis | colour token, blur, spread, intensity |
| `BentoGrid` | Unequal-priority modular layout | columns, gap, item span, responsive rules |
| `MetricTile` | Compact KPI presentation | label, value, unit, trend, status, density |
| `SectionHeader` | Consistent section hierarchy | title, description, actions, eyebrow |
| `PageHeader` | Page identity and primary action | title, breadcrumb, context, actions |
| `SidebarShell` | Responsive application navigation | width, collapsed state, groups, breakpoint |
| `WorkspaceSplit` | Main workspace plus inspector | ratio, min widths, dock/collapse behaviour |
| `EmptyState` | Helpful no-content state | icon, title, description, action |
| `SkeletonBlock` | Layout-preserving loading placeholder | shape, dimensions, animation mode |
| `StatusPill` | Compact semantic status | status token, label, icon |
| `ChartFrame` | Consistent chart container | title, subtitle, legend, source, actions |
| `FloatingToolbar` | Contextual tools near work surface | placement, density, keyboard behaviour |
| `DashboardFrame` | Constrains and spaces a document-led dashboard | max width, density, page padding, section gap |
| `Callout` | Semantic highlighted content block | tone, title, icon, collapsible, border placement |
| `NavigationLink` | Clear, keyboard-accessible destination link | current state, description, icon, density |
| `ReadOnlyBanner` | Persistent disclosure that a view cannot mutate source data | tone, message, optional provenance text |

## Styling contract
- Style components consume semantic tokens and expose documented variants.
- Components do not define their own product-specific brand palette.
- Effects must be configurable and have safe defaults.
- Avoid global element selectors that leak styles into host applications.
- Prefer CSS variables and component-scoped classes.
- Provide `data-theme` and `data-variant` hooks where useful.
- Every style component must have responsive, focus, disabled and reduced-motion behaviour where applicable.

## Document-led dashboard primitives

`DashboardFrame`, `Callout`, `NavigationLink` and `ReadOnlyBanner` are framework-neutral visual primitives. They complement (rather than replace) the functional `Alert`, `Accordion`, `DataTable`, `MetricCard` and navigation components in the component registry.

- `DashboardFrame` provides a readable content measure, consistent page padding and vertical rhythm. It must preserve source reading order.
- `Callout` uses semantic intent (`info`, `success`, `warning`, `critical`, `neutral`) and must not communicate meaning by colour alone. A host-native Markdown callout may be used as the rendering adapter.
- `NavigationLink` remains a real link with a destination, accessible name, visible focus and current-location semantics. Do not replace links with inert styled containers.
- `ReadOnlyBanner` is a persistent disclosure, not an authorization mechanism. The underlying renderer must independently omit write operations.

These primitives are suitable for document dashboards, knowledge workspaces and operational reporting interfaces without requiring app-specific business logic.

## Glass treatment
Use glass as a surface variant, not a separate app identity. Recommended use: floating navigation, overlays, contextual toolbars and selected feature panels. Avoid glass on every card or behind dense text. Include an opaque fallback.

## Bento layout
Use grid spans to express information priority. Ensure reading order remains logical when the grid collapses. Avoid masonry-like visual order that differs from keyboard and screen-reader order.

## Example API (framework-neutral)
```ts
type SurfaceProps = {
  tone?: "default" | "subtle" | "raised";
  elevation?: "none" | "low" | "medium" | "high";
  radius?: "sm" | "md" | "lg" | "xl";
  border?: "none" | "subtle" | "strong";
};

type GlassSurfaceProps = SurfaceProps & {
  blur?: "sm" | "md" | "lg";
  opacity?: number;
  fallback?: "surface-1" | "surface-2";
};

type BentoGridProps = {
  columns?: number;
  gap?: "sm" | "md" | "lg";
  responsive?: "stack" | "auto-fit";
};
```

## Acceptance
A style component is reusable only if it can be applied to at least two unrelated application contexts without code changes beyond token configuration and content.
