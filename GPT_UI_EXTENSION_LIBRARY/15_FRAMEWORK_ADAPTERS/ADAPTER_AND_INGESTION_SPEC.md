---
author: "Genesis"
generated_by: "Genesis"
---
# Framework Adapter and User Library Ingestion Specification

## Supported source families
The library must support user-supplied design systems, component libraries and templates including:
- Bootstrap
- React component libraries
- Tailwind CSS and utility conventions
- shadcn/ui
- Material UI
- Ant Design
- Custom CSS, design tokens, component packages and project templates

This is a source-ingestion requirement, not a claim that every framework is bundled or installed.

## Ingestion workflow
1. **Receive:** accept permitted source formats (repository/archive, CSS, JSON tokens, component documentation, templates).
2. **Inventory:** enumerate files, package metadata, versions, framework/runtime, license and dependencies.
3. **Classify:** identify tokens, components, primitives, layouts, patterns, examples and assets.
4. **Extract contracts:** props, events, slots, variants, states, accessibility and responsive behaviour.
5. **Normalize:** map source definitions to the framework-neutral component schema without destroying source terminology.
6. **Preserve provenance:** retain original package, version, path, source URL or archive name, license and extraction timestamp where available.
7. **Build manifest:** generate machine-readable inventory and dependency graph.
8. **Validate:** check parseability, missing dependencies, duplicate IDs, license constraints and broken references.
9. **Select:** allow a project to choose one or more compatible libraries/design systems.
10. **Compose:** generate the app using the selected source library; avoid silently mixing conflicting design systems.
11. **Report:** provide ingestion summary, warnings, unsupported files and unresolved dependencies.

## Required manifest fields
`id`, `name`, `source_type`, `source_version`, `framework`, `runtime`, `license`, `source_path`, `component_count`, `token_sets`, `dependencies`, `peer_dependencies`, `accessibility_notes`, `responsive_notes`, `ingestion_status`, `validation_findings`.

Unknown fields remain unknown. Do not invent license terms or infer compatibility from a package name alone.

## Project-level selection
Each project declares:
- selected component library/libraries;
- selected theme/token set;
- framework and runtime;
- allowed dependency versions;
- component overrides;
- adapter mapping;
- source provenance.

## Compatibility rules
- React component packages are not automatically compatible with non-React runtimes.
- Tailwind utility classes require the matching build/configuration pipeline.
- shadcn/ui components require their source code and expected dependencies; they are not a hosted component service.
- Bootstrap, Material UI and Ant Design have distinct styling and interaction conventions; avoid mixing them without an explicit integration plan.
- Custom templates retain their own license and attribution requirements.
- Never strip license files or attribution notices during ingestion.

## Output
Produce an inventory, normalized component manifest, adapter mapping, dependency report, license report and validation report. Keep source package and normalized library definitions traceable.
