---
title: Mount and Resume Instructions
version: 1.1.0
updated: 2026-11-24
status: portable-operating-instruction
---

# Mount and Resume Instructions

## Purpose

Make this library usable in a separate ChatGPT account or assistant workspace without relying on the original account's memory or conversation history.

## Recommended ChatGPT installation

For a ChatGPT Project, upload `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` as a Project source and paste `CHATGPT_INSTRUCTIONS.md` into Project instructions. For an eligible custom GPT, use the same files in the GPT's Instructions and Knowledge fields. See `CHATGPT_SETUP.md` for current setup steps and availability caveats.

## Mount procedure

When the user says `Mount UI extension library`:

1. Locate and inspect `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` or, if unavailable, the individual canonical source files.
2. Read the primary `INSTRUCT.md`, architecture specification, component registry, theme presets, layout registry and ChatGPT visual adapter from the available knowledge.
3. Confirm the library specification version, component-family count, component-contract count, theme count, layout count and available app profiles from source files.
4. Report which sections are fully accessible, partially indexed or unavailable.
5. Identify any registry or version inconsistencies. Do not infer missing counts.
6. Apply the automatic UI enhancement behaviour in `INSTRUCT.md` to subsequent relevant requests.

## Mount response contract

Report:

- Library specification version and update date.
- Component families and component contracts.
- Available themes and layout patterns.
- Available rendering adapters and known limitations.
- Whether the consolidated bundle or individual source files were accessible.
- Any missing files or inconsistencies.

Do not claim that executable software has been installed merely because reference files were uploaded.

## Behaviour verification

After mounting, test at least these cases:

- Interface-shaped content: render a useful dashboard or structured interface automatically.
- Existing UI: improve visual presentation while preserving meaning and functionality.
- Ordinary factual question: answer normally without forcing a dashboard.
- Missing runtime capability: provide a supported fallback and disclose the limitation.

## Resume protocol

When a later chat says `resume UI library`, `use mounted UI library` or asks to build an app:

1. Re-read relevant registry and component contracts if they are not available in current context.
2. Identify the requested task, data sources and interactions.
3. Reuse existing components and themes before proposing new ones.
4. Keep app-specific configuration separate from shared components.
5. Render an interface when it materially improves the task and the host supports it; otherwise use the documented fallback.

## Portability boundary

The archive does not transfer account memory, conversation history, private files, credentials, connector authorisations or runtime permissions. Each destination environment must be granted access to the library independently.
