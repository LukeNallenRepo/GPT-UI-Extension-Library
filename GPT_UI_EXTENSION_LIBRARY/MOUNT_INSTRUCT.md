---
author: "Luke Nallen"
---

# Mount and Resume Instructions

## Automatic mount trigger

Every upload of a package clearly identified as GPT UI Extension Library is a mount/reload event. Mount automatically on first upload, repeated uploads, replacements, updated versions and instruction-only updates. Do not wait for a separate command unless the user explicitly requests a file-only edit or says not to mount.

## Mandatory procedure

1. Inspect the incoming archive/folder and identify the actual package root.
2. Read the incoming root `INSTRUCT.md` first.
3. Verify access to the knowledge bundle, component registry, design system and theme presets, layout registry, generic app profiles and host adapters.
4. Activate the incoming version only after successful inspection.
5. Display the required status indicator on every successful mount, even if the same version was previously active.

## Required status indicator

Display this bordered indicator after every successful mount:

**GPT UI EXTENSION LIBRARY:** **ACTIVE**

The library name must be orange and `ACTIVE` green. Enclose both segments together in one visible border. Use the closest supported presentation if colour styling is unavailable. Do not display ACTIVE after a failed or incomplete mount. Do not add a gate, logs, file lists or a diagnostic report unless explicitly requested or needed to explain a failure.

## Mount scope and limits

The package is standalone. Do not require A.I Master or any external product, agent, tool, repository, directory, account memory or connector.

Mounting makes the supplied instructions and reference resources available in the current supported workspace; it does not install executable software or grant permissions. For ongoing automatic UI behaviour in a Project or eligible custom GPT, install `CHATGPT_INSTRUCTIONS.md` and make `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` available as knowledge. The behaviour applies only in that configured workspace, not globally across ChatGPT.

## Resume

When the user says `resume UI library`, `use mounted UI library`, or requests an interface:
- consult the relevant component, theme, layout and generic profile contracts;
- reuse existing components before inventing new ones;
- preserve supplied data, meaning and working behaviour;
- render the strongest interface supported by the host;
- disclose material host limitations and use a structured fallback where necessary.
