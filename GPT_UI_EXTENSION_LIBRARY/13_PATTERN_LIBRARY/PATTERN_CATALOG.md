---
author: "Genesis"
generated_by: "Genesis"
---
# Universal UI Pattern Catalogue

## Application and workspace patterns
- **Command centre:** operational status, priority queue, alerts, recent activity and quick actions.
- **Workspace switcher:** switch among projects, environments or workspaces without confusing identity or permissions.
- **Multi-tab workspace:** preserve context across open resources; disclose unsaved changes before closing.
- **Split workspace:** primary work surface plus contextual inspector; stack on narrow screens.
- **Resource browser:** searchable, filterable collection with preview, metadata and version history.
- **Document dashboard:** document navigation, source content, contextual metadata and related resources.
- **Project overview:** purpose, status, milestones, tasks, dependencies, files and activity.
- **Operations board:** grouped work queues, owners, status, priority and due dates.
- **Approval queue:** pending decision, evidence, requester, impact, decision actions and audit trail.

## Data and analytical patterns
- KPI overview with definition, unit, period, source and comparison baseline.
- Filter → segment → inspect → export workflow.
- Metric drill-down from summary to underlying records.
- Data quality and freshness panel.
- Scenario comparison with baseline, intervention and outcome.
- Forecast panel with assumptions, uncertainty and confidence labels.
- Network/relationship graph with selected-node inspector.
- Event timeline and time-series comparison.
- Provenance panel separating observed, inferred, estimated and unknown values.

## Agent and automation patterns
- Agent roster with role, capability, availability and current assignment.
- Agent detail inspector with instructions, tools, permissions and execution history.
- Workflow canvas with typed nodes, edges, branches and validation.
- Trigger configuration with event, condition, scope, schedule and action.
- Task manifest with owner, dependencies, acceptance criteria and status.
- Execution console with step log, outputs, errors, retries and cancellation.
- Human approval gate for consequential actions.
- Retry/resume panel that preserves completed steps and records recovery.
- Chain-of-command view showing delegation, escalation and responsibility.
- Run comparison showing configuration/version and output differences.

## Knowledge and document patterns
- Library index with taxonomy, tags, search and filters.
- Document reader with table of contents, section anchors and citations.
- Source comparison and diff view.
- Metadata editor with validation and provenance.
- Research pipeline: intake → triage → extraction → synthesis → review → release.
- Evidence ledger with source, claim, confidence, date and supporting excerpt.
- Release candidate panel with validation findings and blockers.
- Book/manuscript workflow with chapter structure, editorial status, revision and proofing gates.

## Creative and media patterns
- Editor shell with tool rail, canvas, inspector and timeline.
- Layer/track list with visibility, mute, lock and ordering.
- Asset browser with preview, metadata and import state.
- Audio waveform/spectrum with playhead and selection.
- Preset browser and non-destructive parameter inspector.
- Version comparison and export queue.
- Creative brief → draft → review → revision → delivery flow.

## Commerce and service patterns
- Product catalogue, category navigation, filters and comparison.
- Product detail with options, availability and transparent pricing.
- Cart/checkout stepper with validation and order summary.
- Store operations dashboard with orders, fulfilment, stock and exceptions.
- Multi-location overview with location-level drill-down.
- Customer support queue with SLA, owner, status and conversation history.

## Learning and behavioural patterns
- Interactive concept explorer with node-specific detail.
- Stepwise learning path and progress checkpoints.
- Reflection prompt and journal capture.
- Scenario simulator with explicit assumptions and repeatable inputs.
- Before/after comparison that distinguishes measured from hypothetical outcomes.
- Progression tree with locked/unlocked state only when backed by actual rules.

## Interface state patterns
All interactive surfaces should specify: initial, loading, ready, empty, filtered-empty, error, offline, stale, disabled, permission-denied, submitting, success-confirmed and partial-success states where relevant.
