---
author: "Luke Nallen"
---

# Install in ChatGPT

This library is a portable set of instructions, registries, design specifications and examples. It is not a software plugin and does not install executable React components or change ChatGPT's global interface. It guides the assistant's responses inside the Project or GPT where it is loaded.

## Recommended: ChatGPT Project

1. Download `15_GPT_UI_extension_library.zip` from the GitHub repository and extract it.
2. In ChatGPT, create a new Project.
3. Upload `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` from the extracted folder as a Project source. This single consolidated file is designed to avoid multi-file upload limits.
4. Open the Project menu, choose **Project settings**, and paste the complete contents of `CHATGPT_INSTRUCTIONS.md` into Project instructions.
5. Start a new chat in the Project and send: `Mount UI extension library`.
6. Ask for a test, for example: `Turn this project status into a polished responsive dashboard: 12 tasks, 8 complete, 3 active, 1 blocked.`
7. Check that the assistant uses a suitable layout and theme, labels the supplied figures as user-provided, and does not claim that controls or persistence exist unless they do.

Project sources and Project instructions serve different purposes: the knowledge bundle supplies reference material; the instruction text establishes default behaviour. Keep both.

## Custom GPT (where creation or editing is available)

1. Open the GPT editor on the ChatGPT web experience, if your account and workspace currently permit GPT creation or editing.
2. Paste `CHATGPT_INSTRUCTIONS.md` into the GPT's **Instructions** field.
3. Upload `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` under **Knowledge**.
4. Save or update the GPT, then test it in Preview with the same sample request above.

Availability of GPT creation and publishing depends on current ChatGPT plan, workspace and product rules. If the GPT editor is unavailable, use the Project method.

## Quick verification prompts

- `Mount UI extension library` — should report the version, registries, themes, layouts and limitations it can actually inspect.
- `Make a dashboard from this status: 12 tasks, 8 complete, 3 active, 1 blocked.` — should create a clear dashboard and label the values as supplied by the user.
- `Improve this existing interface without changing its functionality: [paste interface]` — should preserve semantics and behaviour while improving presentation.
- `Explain photosynthesis in two sentences.` — should answer normally, not force a dashboard.

## What installation does and does not do

**It does:** provide a portable visual vocabulary, component contracts, themes, layouts, examples and response instructions to the selected Project or GPT.

**It does not:** install code, create a React runtime, add new native ChatGPT controls, grant access to external files or apps, transfer memory or permissions, or apply to chats outside the configured Project/GPT. Actual rendering depends on the capabilities of the ChatGPT surface and selected model.

## Updating

When a new release is published, replace the Project/GPT knowledge file with the new `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` and review the corresponding `CHATGPT_INSTRUCTIONS.md`. For a Project, update Project instructions as needed.
