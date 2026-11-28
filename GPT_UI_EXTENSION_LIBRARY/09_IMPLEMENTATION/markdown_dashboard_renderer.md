---
title: Markdown Document and Dashboard Renderer
component: MarkdownDocumentRenderer
version: 1.0
updated: 2026-11-23
status: reusable-integration-pattern
author: "Luke Nallen"
---

# Markdown Document and Dashboard Renderer

## Purpose

A reusable rendering pattern for presenting an existing Markdown document as a navigable application view rather than a plain-text summary. `MarkdownDashboardRenderer` is the dashboard-oriented composition of `MarkdownDocumentRenderer`.

This is an integration contract, not a mandate to add a particular framework or dependency. Use the host application's native Markdown renderer where one exists. Keep the renderer separate from source storage, domain logic and application-specific visual configuration.

## Composition

The renderer composes existing library components instead of redefining them:

- `DashboardFrame` — page measure, padding and section rhythm.
- `PageHeader` / `SectionHeader` — document identity and hierarchy.
- `MetricTile` — compact numeric or categorical snapshots when the source supports them.
- `Alert` / `Callout` — semantic notices and contextual disclosures.
- `DataTable` — source tables with responsive overflow or an intentional mobile alternative.
- `Accordion` — progressive disclosure for secondary material.
- `NavigationLink` — genuine links to related source documents.
- `ReadOnlyBanner` — visible disclosure when the view is non-mutating.
- `EmptyState` / `ErrorState` — missing source and rendering failure.

## Required inputs

```ts
type MarkdownDocumentRendererProps = {
  sourceId: string;                 // stable host-native document identifier
  title?: string;
  mode?: "document" | "dashboard";
  readOnly?: boolean;               // defaults to true for dashboard previews
  refreshKey?: string | number;
  onNavigate?: (destination: string) => void;
  renderMarkdown: (source: string, context: RenderContext) => RenderResult;
  loadSource: (sourceId: string) => Promise<string>;
};

type RenderContext = {
  sourceId: string;
  resolveInternalLinks: true;
  allowEmbeds: boolean;
  readOnly: boolean;
};
```

The host adapter owns `loadSource`, native Markdown parsing, internal-link resolution and lifecycle cleanup. The component must not guess file paths or convert internal links into unverified URLs.

## Behaviour contract

1. Load the canonical Markdown source without modifying it.
2. Render Markdown using the host-native parser where available, preserving headings, lists, tables, blockquotes, callouts/admonitions, code blocks, embeds and collapsible sections supported by that host.
3. Resolve internal links against the original source context so relative paths and wiki-link semantics remain valid.
4. Keep external links distinguishable from internal navigation and apply the host's normal permission and confirmation behaviour.
5. Re-render on explicit refresh or source-change events; cancel or ignore stale asynchronous renders.
6. Unload observers, subscriptions and renderer components when the view closes.
7. Never write, create, rename, delete or mutate source documents in read-only mode. Do not expose edit actions in the dashboard view.
8. Display an actionable error state if the source is missing or rendering fails; never silently substitute a summary.

## Read-only guarantee

`readOnly` is a capability boundary, not merely a visual label. The adapter must not call host write APIs, and any navigation target must be opened through the host's standard read-only navigation path. If a host cannot guarantee read-only behaviour, it must report that limitation instead of claiming the view is read-only.

## Rendering and fidelity requirements

- Preserve source hierarchy and content order; do not rewrite the Markdown as part of rendering.
- Render host-native callouts/admonitions with their semantic type and title.
- Render tables as semantic tables with header associations; provide horizontal scrolling or a documented stacked alternative on narrow screens.
- Render collapsible Markdown sections using accessible disclosure controls with keyboard support.
- Internal links must remain functional host-native links, not decorative buttons.
- Preserve code formatting and language labels where supported.
- Do not invent values, freshness, clinical interpretation or other data absent from the source.
- Show provenance and record currency where they exist in the source.

## States

| State | Required presentation |
|---|---|
| Loading | Stable frame and non-misleading loading indicator |
| Ready | Native Markdown output in the dashboard frame |
| Empty | Explain that the source has no content; do not fabricate dashboard data |
| Missing | Show the unresolved source identifier and recovery guidance |
| Error | Show render failure without discarding the source |
| Stale | Indicate source freshness only when the host can establish it |
| Read-only | Persistent disclosure and no mutation controls |

## Accessibility and responsive behaviour

- Preserve semantic heading levels and landmark structure.
- Keep link destinations and labels accessible to assistive technology.
- Ensure all disclosures and navigation work by keyboard with visible focus.
- Maintain text contrast in light, dark and high-contrast themes.
- Keep reading order identical to visual order.
- At mobile widths, constrain page padding, allow tables to scroll intentionally and avoid horizontal page overflow.
- Respect `prefers-reduced-motion`.

## Host adapter: Obsidian

The Obsidian adapter should use the public `MarkdownRenderer` API with the source file path as the render context. This is necessary for Obsidian callouts, internal wiki links, embeds and vault-relative links to resolve correctly. A custom `ItemView` can provide the dashboard frame and a dedicated content target. The adapter should unload its `Component` on refresh/close, watch only the canonical source for updates, and expose open/refresh commands.

For a read-only Obsidian dashboard, the adapter should only call vault read APIs and `MarkdownRenderer.render`; it must not call `vault.modify`, `vault.create`, `vault.delete`, `vault.rename` or other write APIs. Keep plugin-specific code in the target vault, not in this generic library. The library documents the contract and reusable primitives only.

## Examples of reuse

- A medication log dashboard: historical record, callouts, metric tiles, linked source records; sensitive values remain source-backed and unaltered.
- A project operations dashboard: project status, task tables, expandable notes and links to canonical project records.
- A research notebook dashboard: evidence summary, semantic notices, tables and references to source notes.

These examples share the renderer and primitives; each application supplies its own source, content and thin theme configuration.

## Verification checklist

- [ ] Source loaded from the canonical identifier.
- [ ] Source content remains unchanged after opening and refreshing.
- [ ] Internal links resolve in host context.
- [ ] Callouts/admonitions render with semantic type.
- [ ] Tables remain usable at mobile widths.
- [ ] Collapsible sections are keyboard accessible.
- [ ] Missing-source and render-error states are visible.
- [ ] Refresh does not duplicate content or subscriptions.
- [ ] Close/unmount releases listeners and renderer resources.
- [ ] No host write API is called in read-only mode.
