# Universal GPT App UI Extension Registry

**Version:** 1.0\
**Compiled:** 2026-11-14\
**Purpose:** Portable inventory and implementation specification for
reusable UI components across the user's GPT applications and connected
software projects.

## 1. Scope and evidence status

This registry consolidates UI capabilities documented in available
project history. It is an integration inventory, not proof that every
listed component has been implemented or shipped. The Karma Circle and
Behaviour OS have the strongest documented component inventories.
Genesis Forge, Questmaster and Warden have documented workflow
requirements, but their complete implemented UI sets require source-code
verification.

Status labels: - **Documented:** explicitly present in prior project
descriptions or architecture. - **Workflow-derived:** interface
component inferred from a documented workflow requirement;
implementation not verified. - **Proposed:** reusable enhancement
recommended for the shared library.

## 2. Application inventory

### The Karma Circle --- Documented

-   Application header, logo, navigation tabs, synchronisation
    indicator, version badge and close action.
-   Framework information cards.
-   18-node KC-MV24 Karma Circle visualiser.
-   Simulator and scenario controls.
-   Probability weighting.
-   Resonance engine and Resonance/Dissonance indicators.
-   Trajectory forecasts.
-   Insight engine and intervention engine.
-   Attention drivers and perception/behaviour insights.
-   Achievements, Karma Score, daily challenges and identity paths.
-   Quest system, identity vector and reflection journal.

### Behaviour OS --- Documented / Proposed modules

-   Core Loop.
-   State Analysis.
-   Intervention.
-   Gamification.
-   Simulation.
-   Behaviour/perception arcs.
-   Current State → Intervention → Projected Outcome flow.
-   Resonance, Dissonance, Emotional Resonance, confidence and likely
    trajectory indicators.
-   Modular, independently movable and crop/overlay-friendly panels.

### Genesis Forge --- Workflow-derived

-   Natural-language project creation entry point.
-   Project creation, agent creation and skill creation workflows.
-   Project workspace and project overview.
-   Knowledge reconstruction/import workflow.
-   Source/provenance review and project index.
-   Agent and skill catalogue.
-   Import progress, validation results and unresolved-source panels.

### Questmaster --- Workflow-derived

-   Weekly task manifest and weekly output view.
-   Individual task queue under `/tasks`.
-   Agent role and assignment cards.
-   Activation trigger definitions and status.
-   Batch execution view.
-   Task status, dependencies, outputs and blockers.
-   Execution summary and handoff report.
-   Distinguish the weekly executable manifest from standalone
    individual tasks.

### Warden --- Workflow-derived

-   Incoming resource intake queue for files downloaded or imported from
    GPTs and other AI systems.
-   Resource type and project identification.
-   Metadata extraction and validation.
-   Canonical naming preview and approval.
-   Version and provenance management.
-   Canonical destination selection.
-   Global resource registry and project index updates.
-   Reference repair/update report.
-   Duplicate detection and conflict resolution.

### LocalForge --- Documented project architecture

-   Code editor.
-   File explorer and project navigation.
-   Terminal / command execution panel.
-   Run and stop controls.
-   Application preview.
-   Backend/API status panel.
-   File read/write and project status workflows.
-   Known project architecture: React + Vite + TypeScript, with a Node
    backend and endpoints for files, status and execution.

### Lucifer's Language / THE GAME --- Conceptual and workflow-derived

-   Audio player and playback controls.
-   Waveform and audio-pattern visualiser.
-   Symbol/glyph display.
-   Clue and puzzle panels.
-   Interactive discovery sequence.
-   Player progress and participation state.
-   Shared narrative / world-state display.
-   Keep experimental audio claims distinct from fictional or ARG
    presentation.

## 3. Universal component catalogue

### Navigation and application shell

-   `AppShell`
-   `AppHeader`
-   `Sidebar`
-   `NavigationGroup`
-   `Breadcrumbs`
-   `ProjectSwitcher`
-   `WorkspaceTabs`
-   `CommandPalette`
-   `ContextMenu`
-   `NotificationCenter`
-   `ActivityFeed`
-   `VersionIndicator`
-   `SyncStatus`

### Dashboard and information

-   `DashboardGrid`
-   `MetricCard`
-   `KpiCard`
-   `StatusBadge`
-   `ProgressBar`
-   `CircularProgress`
-   `Timeline`
-   `DataTable`
-   `SearchableList`
-   `FilterBar`
-   `SortControl`
-   `ExpandablePanel`
-   `ComparisonPanel`
-   `SystemHealthCard`

### Visualisation

-   `NodeGraph`
-   `RelationshipCircle`
-   `NetworkGraph`
-   `FeedbackLoop`
-   `StateTransition`
-   `ProbabilityDistribution`
-   `ResonanceGauge`
-   `TrajectoryChart`
-   `Heatmap`
-   `TimeSeriesChart`
-   `Waveform`
-   `AudioSpectrum`
-   `HierarchyTree`

### Agents and workflows

-   `AgentCard`
-   `AgentStatus`
-   `RoleAssignment`
-   `TriggerEditor`
-   `TaskQueue`
-   `TaskManifest`
-   `ExecutionLog`
-   `WorkflowCanvas`
-   `CommunicationStream`
-   `ApprovalPanel`
-   `RetryPanel`
-   `BatchRunControls`
-   `WeeklyReport`

### Resources and knowledge

-   `FileExplorer`
-   `ResourceRegistry`
-   `MetadataEditor`
-   `VersionHistory`
-   `ProvenanceViewer`
-   `DocumentPreview`
-   `ImportExport`
-   `DependencyGraph`
-   `KnowledgeGraph`
-   `SearchResults`
-   `ValidationPanel`
-   `NamingPreview`

### Interactive experiences

-   `SimulationControls`
-   `ScenarioBuilder`
-   `Questionnaire`
-   `ReflectionJournal`
-   `AchievementCard`
-   `QuestCard`
-   `ChallengeCard`
-   `AudioPlayer`
-   `WaveformControls`
-   `InteractiveNode`
-   `LiveOutputPanel`

## 4. Shared visual design system

### Base visual language

-   Dark backgrounds: near-black, charcoal and deep navy.
-   Primary accents: electric violet and cyan.
-   Secondary accents: magenta, blue and restrained orange.
-   Cards: layered dark surfaces, subtle translucency and clear
    hierarchy.
-   Borders: fine outlines, restrained gradients and controlled glow.
-   Typography: readable geometric sans-serif; use display typography
    sparingly.
-   Icons: one consistent icon family and stroke weight.
-   Motion: purposeful transitions, state changes and feedback; respect
    reduced-motion preferences.
-   Layout: responsive grids, resizable panels where useful, consistent
    spacing and alignment.
-   Accessibility: readable contrast, keyboard navigation, visible
    focus, semantic labels and non-colour status indicators.

### Project themes

-   Karma Circle: cyan, magenta and red.
-   Behaviour OS: indigo and white.
-   Lucifer's Language: violet and audio-led visualisations.
-   THE GAME: blue and purple.
-   Ascension: cosmic, neon and geometric identity.
-   Genesis Forge / Questmaster / Warden: dark operational workspace
    with violet/cyan accents; distinguish each tool through iconography
    and accent details rather than separate incompatible design systems.

### Brand asset rule

Canonical logos, sigils and approved source artwork must be stored as
independent assets. Do not redraw or distort them as part of ordinary
component styling. Glow, blur, gradients and decorative framing should
be separate layers.

## 5. Recommended implementation architecture

Use a framework-independent component specification, with a React
implementation as the first adapter.

``` text
ui-extension-library/
  registry/
    extensions.json
    components.json
    themes.json
  core/
    tokens/
    typography/
    icons/
    motion/
    accessibility/
  components/
    navigation/
    dashboard/
    data-visualisation/
    agents/
    workflows/
    resources/
    interactive/
  layouts/
    app-shell/
    dashboard/
    workspace/
    split-pane/
  themes/
    ascension/
    karma-circle/
    behaviour-os/
    lucifers-language/
    the-game/
    operations/
  adapters/
    react/
    web-components/
  examples/
    karma-circle/
    behaviour-os/
    genesis-forge/
    questmaster/
    warden/
    localforge/
    lucifers-language/
```

Suggested React foundation, based on the existing Karma Circle
architecture: - React + TypeScript + Vite. - Tailwind CSS for utility
styling and theme tokens. - Framer Motion for optional motion. - Zustand
for shared client state where needed. - React Router for application
navigation. - Lucide icons. - Recharts for conventional charts;
specialised graph/audio components should use suitable dedicated
renderers.

These are recommended shared-library choices, not a claim that every
existing GPT app already uses this exact stack.

## 6. Extension contract

Each extension should declare: - Stable extension ID and semantic
version. - Display name and description. - Component exports. - Required
and optional dependencies. - Accepted properties and events. - State
ownership and persistence requirements. - Theme tokens consumed. -
Accessibility behaviour. - Responsive behaviour. - Data input/output
contract. - Permissions, if any. - Example usage and test coverage.

Example manifest:

``` json
{
  "id": "visualisation.resonance-gauge",
  "name": "Resonance Gauge",
  "version": "1.0.0",
  "category": "data-visualisation",
  "status": "documented-design",
  "framework": "react",
  "exports": ["ResonanceGauge"],
  "themeTokens": [
    "surface.panel",
    "accent.primary",
    "status.positive",
    "status.warning"
  ],
  "accessibility": {
    "keyboard": true,
    "textAlternative": true,
    "colourIndependentStatus": true
  }
}
```

## 7. Import and integration principles

1.  Import the shared tokens and component package before importing
    application-specific components.
2.  Keep business logic and domain models outside the presentation
    layer.
3.  Give every component typed inputs and documented outputs.
4.  Allow themes to change appearance without changing component
    behaviour.
5.  Keep components independently reusable and composable.
6.  Use adapters for framework-specific implementations.
7.  Version components independently where practical.
8.  Avoid duplicating components that already exist in the registry.
9.  Preserve source provenance and identify whether an extension is
    documented, workflow-derived, proposed or implementation-verified.
10. Validate imports, dependencies, accessibility and responsive
    behaviour in the target application.

## 8. Visual enhancement backlog

Recommended enhancements for the shared library: - Resizable and
dockable panels. - Optional glass-like surfaces and layered depth. -
Context-sensitive glow and active-state illumination. - Animated graph
connections and node focus. - Smooth chart transitions. - Skeleton
loading and progressive data rendering. - Command palette and keyboard
shortcuts. - Drag-and-drop workspace composition. - Expandable detail
views and contextual inspectors. - Light/dark theme support, while
retaining the dark Ascension default. - Reduced-motion mode and
accessibility controls. - Consistent empty, loading, success, warning
and error states.

## 9. Verification gaps

The following require source-level inspection before being labelled
implemented: - Complete list of GPT applications and their actual
registered UI extensions. - Actual code and dependency versions for each
app. - Whether the proposed Genesis Forge, Questmaster and Warden panels
exist in working interfaces. - Exact component properties, events and
data contracts. - Which components are duplicated across applications
and which are unique. - Current deployment and runtime status.

**Registry principle:** this document is the portable integration
specification. It should be updated from actual source repositories and
app exports as they are inspected; it must not convert proposed UI into
falsely reported implementation history.
