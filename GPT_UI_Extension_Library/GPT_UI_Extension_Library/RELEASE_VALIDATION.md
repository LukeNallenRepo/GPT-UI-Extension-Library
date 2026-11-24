# Release Validation Report

**Validation date:** 2026-11-24  
**Repository release:** 1.1.0  
**Library specification:** 2.3.0  
**Licence:** Custom Free Use, Modification and Non-Sale Licence — retained unchanged.

## Results

| Check | Result | Evidence / scope |
|---|---|---|
| Source ZIP integrity | PASS | Source archive CRC test completed before extraction. |
| Output ZIP integrity | PASS | Reopened and CRC-tested after archive creation. |
| Repository root layout | PASS | `README.md`, `LICENSE.md`, `INSTRUCT.md` and project directories are at archive root; no duplicated project directory prefix remains. |
| Duplicate README variants | PASS | `README.md` is the only root README; no `README_updated.md` or numbered duplicate remains. Legacy README retained only under `archive/legacy/`. |
| Historical material isolation | PASS | Historical working drafts remain under `archive/legacy/`; no embedded nested project ZIP was included. |
| Licence preservation | PASS | `LICENSE.md` retains the custom Luke Nallen Free Use, Modification and Non-Sale Licence text. It is not the standard MIT licence or an OSI-approved open-source licence. |
| JSON syntax | PASS | All 3 JSON files parsed successfully. |
| Local Markdown links | PASS | All relative Markdown file links were checked against the flattened archive; no missing local targets found. External URLs were not fetched. |
| Consolidated knowledge bundle | PASS | `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` is present; embedded profile paths were adjusted to the repository-root layout. |
| ChatGPT setup documentation | PASS | Project and custom GPT setup steps are present in `CHATGPT_SETUP.md`. |
| Automatic UI enhancement policy | PASS | Default enhancement behaviour is specified in `INSTRUCT.md` and the copy/paste instruction file. |
| Clean-workspace procedure review | PASS — DOCUMENT REVIEW ONLY | Installation steps and test prompts were reviewed for consistency. This is not a live ChatGPT workspace test. |
| Independent ChatGPT installation | OUTSTANDING | Not performed. Requires a separate ChatGPT account/workspace and manual UI access. |

## Registry counts read from source JSON

- Component families: 18
- Component contracts: 32
- Theme presets: 7
- Application profiles: 19
- Layout patterns: 10 (documented in the layout registry; not independently executed or runtime-tested)

These are registry/documentation counts, not proof that each entry is a separately executable component.

## Validation method and limitations

The release archive was rebuilt from the canonical project directory, with its duplicated outer directory level removed. Checks covered ZIP CRC integrity, required root files, duplicate README names, nested project paths, JSON parsing and relative Markdown links. No application build, runtime rendering test, GPT publication test, or external account installation was performed.

The library is an instruction/specification resource, not an executable ChatGPT plugin or React package. Rendering and interaction depend on the ChatGPT surface, model and available capabilities. Project/GPT feature availability is controlled by current ChatGPT plan, workspace and product rules.

## Independent installation test still required

On a separate ChatGPT account or workspace:

1. Create a Project and upload `GPT_UI_EXTENSION_LIBRARY_KNOWLEDGE.md` as a Project source.
2. Paste `CHATGPT_INSTRUCTIONS.md` into Project instructions.
3. Start a new chat and send `Mount UI extension library`.
4. Test an operational status prompt, an existing-UI improvement prompt and an ordinary factual question.
5. Record the actual rendering, limitations and any missing knowledge access.

Until that test is completed, cross-account installation remains **UNVERIFIED**.
