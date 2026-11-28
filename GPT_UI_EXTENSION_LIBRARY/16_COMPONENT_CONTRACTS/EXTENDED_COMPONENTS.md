---
author: "Genesis"
generated_by: "Genesis"
---
# Extended Component Contracts

| Component | Purpose | Key contract |
|---|---|---|
| `EvidenceLedger` | Claims and evidence | source, claim, excerpt, confidence, date, status |
| `ProvenanceViewer` | Data lineage | origin, transformations, version, author, timestamp |
| `ScenarioWorkbench` | Repeatable scenario runs | inputs, model version, assumptions, run ID, outputs |
| `BeforeAfterCompare` | Compare states | baseline, changed state, delta, explanation |
| `NodeInspector` | Inspect graph/model node | selected node, definition, values, relations, interventions |
| `NetworkCanvas` | Relationship visualization | nodes, edges, selection, layout, zoom |
| `WorkflowCanvas` | Workflow authoring | nodes, typed edges, branches, validation, execution state |
| `ExecutionTimeline` | Run history | ordered events, timestamps, status, outputs |
| `TaskManifest` | Structured task record | objective, scope, owner, dependencies, acceptance criteria |
| `ApprovalGate` | Human decision | request, evidence, risk, decision, actor, audit record |
| `RetryResumePanel` | Recovery | failed step, retry policy, checkpoint, prior outputs |
| `LibraryImporter` | Import UI libraries | source, inventory, license, dependencies, validation |
| `ComponentPicker` | Select reusable components | search, filters, compatibility, preview, selected version |
| `ThemePicker` | Select themes | preset, preview, contrast notes, brand overrides |
| `DesignTokenInspector` | Inspect tokens | token name, value, semantic role, source |
| `ResponsivePreview` | Preview breakpoints | viewport, layout mode, overflow warnings |
| `VersionDiff` | Compare versions | added, removed, changed, source and compatibility |
| `ReleaseChecklist` | Release readiness | requirement, evidence, result, blocker, reviewer |
| `ChapterNavigator` | Manuscript navigation | chapter, order, word count if supplied, editorial state |
| `EditorialIssueList` | Editing/proofing issues | location, category, severity, comment, resolution |
| `OrderQueue` | Commerce operations | order, channel, status, fulfilment, exception |
| `LocationComparison` | Multi-site operations | location, comparable metric, period, source |

Every contract must additionally define required/optional props, event signatures, state ownership, permission boundary, loading/empty/error/disabled states, keyboard behaviour, mobile layout and adapter availability.
