# Chatbot Instructions for Lux Omni V3

> **Audience:** Any AI assistant or chatbot working on this repository.  
> **Repository:** [LuxrajKayal/Lux-Omni-V3](https://github.com/LuxrajKayal/Lux-Omni-V3)  
> **Primary branch:** `main`  
> **Purpose of this document:** Preserve the developer's workflow rules, project context, and commit-history context across new chat sessions.

---

## 1. Non-Negotiable Rule: Do Not Change Code Without Permission

The developer is learning to build Lux Omni V3 and wants to make changes personally with guidance. Respect that process.

1. **Never edit, create, delete, move, rename, reformat, or overwrite repository files without explicit permission from the developer.**
2. If the developer asks you to **inspect, view, check, explain, review, or teach**, treat the request as read-only. Do not make repository changes or commits.
3. If the developer requests a change to **one named file**, modify that file only. If another file may need a related change, explain why and ask permission before touching it.
4. Do not make opportunistic improvements, clean-ups, refactors, comment edits, formatting changes, or unrelated fixes.
5. Do not remove comments simply because they look unnecessary. Some comments are intentional visual hierarchy markers or learning notes.
6. A request to explain or suggest code **in chat** is not permission to apply that code to the repository.
7. Before a multi-file task, state the exact files you propose to change and get confirmation. Follow any narrower file scope specified by the developer.
8. Treat creating or editing files, committing, pushing, deploying, changing settings, and dismissing security alerts as distinct actions. Do not perform an additional action unless the developer has authorized it. If the requested repository operation necessarily creates a commit, make that fact clear when appropriate.
9. After authorized work, verify the exact files changed and report the result. Never claim a change was made or tested unless it actually was.
10. If permission or scope is ambiguous, stop and ask one direct clarification question.

**The developer's ownership and learning process take priority over speed or unsolicited improvements.**

## 2. Required Onboarding Process for a New Chatbot

Before proposing or making any project change, follow these steps in order.

### Step 1 — Read `FileMap.md`

- Understand the repository's documented directory and file structure.
- Use the existing file and folder responsibilities as the first reference.
- Do not create new files or reorganize the structure just because another layout seems preferable.
- Remember that a file listed in the map may be an empty scaffold or a planned component. Verify its actual contents before relying on it.

### Step 2 — Understand the project goals

- Read the available project documentation, especially `README.md`, `docs/BUILD_LOG.md`, architecture or provider guides, and relevant feature notes.
- The current `README.md` has historically contained only a minimal placeholder, so it may not explain the full goals.
- If the goal, expected behavior, constraints, or acceptance criteria for the current task are unclear, ask the developer. Do not invent requirements.
- Distinguish clearly between a **planned feature**, a **scaffolded file**, and a **working implementation**.

### Step 3 — Read the commit history from the beginning to the current revision

- Inspect the live GitHub history from the initial commit to the latest commit before beginning work. Use the history snapshot later in this file as orientation, not as a substitute for checking current history.
- Read commit messages and, when relevant, the corresponding diffs. Learn why changes were made, what was reverted, what the developer wrote manually, and which approaches were rejected.
- Check the current branch and latest revision. Do not assume this document's history snapshot is still current.
- Never repeat a reverted or explicitly rejected change without discussing it with the developer first.

### Step 4 — Inspect the exact files involved

- Read the current version of every file relevant to the request before advising or changing it.
- Confirm actual paths, selectors, token names, stylesheet references, and current contents.
- Do not rely on remembered snippets, earlier chat content, or stale assumptions when the live repository can be checked.
- If a file cannot be accessed or a detail cannot be verified, state the limitation instead of guessing.

### Step 5 — Discuss the plan and wait for authorization

- Briefly explain the proposed approach and identify the exact files that would change.
- Ask for approval before implementing it.
- If the developer says “don't touch the repo,” “only tell me here,” “view only,” or equivalent, remain strictly read-only.
- Do not interpret silence, a general request for advice, or an earlier authorization as permission for a new change.

## 3. No Hallucinations or Unrequested Cleverness

- Never fabricate repository contents, files, paths, commit history, test results, runtime behavior, or project decisions.
- Do not pretend to have opened or tested the live website when you only inspected source code.
- Separate verified facts, reasonable inferences, and unknowns.
- If unsure, ask a specific question instead of “being smart” by filling in missing requirements.
- Do not claim a feature works solely because a placeholder file exists or a stylesheet is linked.
- When reviewing a bug, explain the evidence and likely cause before proposing a fix.
- Keep explanations understandable to a developer who is learning. Explain new CSS/HTML/JavaScript concepts step by step when asked.
- When the developer says they want to make a change themselves, provide the exact file path, insertion point, code, and explanation—but do not apply it.

## 4. Project Context and Current Architecture

Lux Omni V3 is being developed as a modular, multi-content workspace. The repository's file map and scaffolding indicate intended areas such as:

- Application shell: topbar, sidebar, workspace, viewports, minimized dock, replacement dialog.
- Content features: PDF, Markdown, images, YouTube, clipboard, snipping/capture tools, and temporary logs.
- Storage and providers: local files and planned cloud-provider adapters such as Dropbox, Google Drive, OneDrive, GitHub, and S3.
- Shared JavaScript modules: core registries, state/models, services, adapters, UI, storage, and utilities.
- Theme and design system: shared color tokens, theme-specific semantic variables, typography tokens, and component styles.

This is a description of the intended structure, not a claim that every feature is implemented. Check the current source and documentation before asserting implementation status.

### Third-party vendor directories

- `site/vendor/pdf.js/` contains a vendored Mozilla PDF.js source tree.
- `site/vendor/pdf-lib/` contains a vendored pdf-lib source tree.
- The build log records that these sources were imported from upstream and verified against pinned upstream trees.
- Existing vendor documentation states that these libraries were not yet integrated into the Lux Omni runtime at the time of that documentation. Re-check current source before making a current claim.
- Treat vendor files as third-party upstream source. Do not modify, remove, reformat, or regenerate them without explicit permission and a clear reason.

## 5. CSS Structure and Design-System Conventions

Follow the current `FileMap.md` rather than inventing a new architecture.

### Current CSS responsibilities

- `site/css/foundation/tokens.css`: primitive Lux brand colors, reusable gradients, font-family tokens, and motion values.
- `site/css/foundation/typography.css`: shared font application and reusable typography tokens.
- `site/css/themes/light.css` and `site/css/themes/dark.css`: semantic variables that change with the active theme.
- `site/css/shell/topbar/topbar.css`: topbar layout and topbar-specific styles.
- Other shell, feature, and responsive CSS files should retain their assigned responsibilities.

### Token conventions

- `--lux-*` names identify Lux brand primitives or shared design values.
- `--theme-*` names identify semantic values selected by the active theme.
- Component selectors such as `.lux-topbar`, `.brand`, `.brand-mark`, `.brand-copy`, `.brand-name`, and `.brand-slogan` apply those values to the relevant UI elements.
- Reuse an existing token when it represents the correct meaning. Do not create near-duplicate tokens without a reason.
- A token declaration does not style anything by itself; a consuming CSS rule must reference it.
- For theme-aware styling, inspect both theme files and the current root `data-theme` state.
- Keep the developer's separation of concerns. Do not combine files or move tokens across files without approval.

### Intentional comments in `topbar.css`

The topbar stylesheet contains a note from the developer explaining that numbered comment sections represent **visual hierarchy only**, not actual CSS nesting. Preserve those comments. Do not remove or rewrite them unless the developer explicitly asks.

## 6. Collaboration and Teaching Style

- The developer prefers to work step by step and learn the purpose of changes before proceeding.
- For a learning task, explain one small section at a time and then let the developer confirm before moving ahead.
- Avoid dumping an entire architecture or full implementation when the developer asks about one property or one section.
- When offering code to copy, clearly state the destination file and the exact place where it belongs.
- Respect the developer's existing code and naming conventions, even if you would personally choose another style.
- Do not address the developer by name unless explicitly requested.

## 7. Commit-History Lessons

The messages below are the repository's commit history snapshot checked on **2026-10-17**, ordered oldest to newest. The live history must be checked again at the start of future work; this list is a durable orientation record, not a live source of truth.

Several commits explicitly document the developer's expectations. In particular:

- `3cd38ad` says unused topbar CSS was removed because ChatGPT had written it when the request was only to fix a link.
- `3443b45` reverts PDF diagrams that were added without approval.
- `b56a708` restores the original `FileMap.md`.
- `d5cb480` reverts file-map scaffolding changes.
- The later topbar commits show that the developer is writing and learning the CSS incrementally.
- The typography commits show the intended separation of foundation typography, theme colors, and component-specific styles.

These are practical reminders: **do only what was requested, ask before expanding scope, preserve intentional structure, and never repeat reverted work without permission.**

### Commit messages recorded in the snapshot

| Date (UTC) | Short SHA | Commit message |
|---|---|---|
| 2026-10-14 | `f2fc93c` | Filemap created. |
| 2026-10-14 | `a11379e` | Files added |
| 2026-10-14 | `4c02053` | Add initial HTML structure and create styles.css file |
| 2026-10-14 | `bdbdc23` | Create 107 empty file-map placeholders and update build log |
| 2026-10-14 | `d5cb480` | Revert file-map scaffolding changes |
| 2026-10-14 | `8dce60f` | File map updated to include new features and improvements. |
| 2026-10-14 | `7640401` | Remove unused styles.css file |
| 2026-10-14 | `aecfba1` | Create 143 empty placeholders from updated FileMap |
| 2026-10-14 | `22933d1` | Add README.md for third-party dependencies documentation |
| 2026-10-14 | `9de3dc7` | Add PDF.js and pdf-lib as unmodified vendor submodules |
| 2026-10-14 | `b641e59` | Add temporary one-time vendor import workflow [run-vendor-import] |
| 2026-10-14 | `a8d2a1d` | Import full PDF.js and pdf-lib source into vendor |
| 2026-10-14 | `cb7c234` | Add temporary exact vendor verification workflow [run-vendor-verify] |
| 2026-10-14 | `9738d7b` | Include every upstream-tracked PDF library file |
| 2026-10-14 | `50171c8` | Correct build log and record verified full vendor import |
| 2026-10-14 | `fd5361e` | Enhance HTML structure with additional comments for clarity |
| 2026-10-14 | `fd97381` | Add PDF workflow flowchart and engineering block diagram |
| 2026-10-14 | `3443b45` | Revert PDF diagrams added without approval |
| 2026-10-15 | `5d36612` | Add Lux PDF viewer icon SVG and update index.html to include it |
| 2026-10-15 | `37c9089` | Update FileMap with current repository structure |
| 2026-10-15 | `8773e38` | Configure GitHub Actions deployment for Pages |
| 2026-10-15 | `e9df66d` | Refactor Lux PDF Viewer Icon SVG structure |
| 2026-10-15 | `af21c21` | Add Lux topbar CSS and new Lux Omni icon SVG |
| 2026-10-15 | `993d180` | Add new SVG icons for Lux Omni application and loader |
| 2026-10-15 | `cd8b8b4` | Add new SVG icons for Lux Omni application |
| 2026-10-15 | `0a20c05` | docs: update V3 file map |
| 2026-10-15 | `b56a708` | revert: restore original FileMap.md |
| 2026-10-15 | `27a4c17` | docs: correct icons section in file map |
| 2026-10-15 | `15467e8` | docs: update global header structure and branding details in index.html Svg directory fix |
| 2026-10-15 | `aecfba1` | Create 143 empty placeholders from updated FileMap |
| 2026-10-15 | `d5cb480` | Revert file-map scaffolding changes |
| 2026-10-16 | `d0dc6ea` | docs: enhance index.html with detailed comments and structure for topbar functionality |
| 2026-10-16 | `3085f66` | docs: explain current topbar HTML structure |
| 2026-10-16 | `ba1cec7` | docs: link HTML walkthrough from index |
| 2026-10-16 | `baf9a0b` | docs: fix markdown formatting in HTML guide |
| 2026-10-16 | `d1754a8` | fix: point brand link to V3 homepage |
| 2026-10-16 | `0252d46` | style: group brand logo and text as home link |
| 2026-10-16 | `56b2261` | docs: sync HTML guide with brand home link |
| 2026-10-16 | `3cd38ad` | style: remove unused topbar CSS styles I will write myself , Chatgpt written it while I asked to fix one link |
| 2026-10-16 | `5df9cb5` | style: add initial topbar CSS structure with visual nesting comments |
| 2026-10-16 | `728a1f6` | style: refine comments for visual nesting clarity in topbar CSS |
| 2026-10-16 | `e590397` | style: update topbar section header and enhance CSS structure with detailed comments |
| 2026-10-16 | `e57e677` | style: add theme variables for topbar background and text colors in dark and light modes |
| 2026-10-16 | `ac9bc17` | style: reorder topbar stylesheet links for improved organization |
| 2026-10-16 | `0535777` | style: update light theme CSS to include root selector for topbar background |
| 2026-10-16 | `2462619` | style: update dark and light theme CSS to remove root selector for topbar background |
| 2026-10-16 | `ecb86ac` | style: add brand identity styles to topbar CSS for improved layout and design |
| 2026-10-17 | `ddc2045` | style: enhance design tokens with additional gradients, typography, and motion variables |
| 2026-10-17 | `608fbad` | style: add foundation typography stylesheet |
| 2026-10-17 | `e25e947` | docs: add typography stylesheet to file map |
| 2026-10-17 | `777c11c` | style: add brand typography tokens to typography stylesheet |
| 2026-10-17 | `0086dc7` | style: add muted text styles for topbar in dark and light themes |
| 2026-10-17 | `efd96dc` | style: add brand text styles for improved topbar layout |
| 2026-10-17 | `f585793` | style: update title and brand name to include 'Workspace' for consistency |
| 2026-10-17 | `5db6b8e` | style: fix typo in white-space property and add brand slogan styles |
| 2026-10-17 | `89e52cb` | style: add inherit color property to brand class for consistency. This prevents the browser's default link color from overriding the topbar's intended text color. |

**History note:** This snapshot preserves commit messages that were returned by GitHub during the 2026-10-17 inspection. Some old scaffold/revert records may be repeated or appear out of chronological context in this snapshot because Git history contains independent branches/reverts; use the live chronological log and commit diffs to determine exact ancestry. Never assume that this table replaces the live commit graph.

## 8. Current Working Context at the Time This Document Was Written

The last inspected work was focused on the topbar and its typography.

- The topbar selector is `.lux-topbar` in `site/css/shell/topbar/topbar.css`.
- The logo uses `.brand`, `.brand-mark`, and `.brand-mark img`.
- The brand text uses `.brand-copy`, `.brand-name`, and `.brand-slogan`.
- `typography.css` contains the shared font-family rules and tokens for brand name/slogan typography.
- The light and dark theme files define `--theme-topbar-bg`, `--theme-topbar-text`, and `--theme-topbar-muted`.
- `index.html` currently uses `data-theme="dark"` and links to the theme, typography, token, and topbar stylesheets.
- The developer was about to learn the typography token changes one by one. Do not jump ahead or modify code unless asked.

Always re-fetch these files before relying on this snapshot, because the repository may have changed since this document was written.

## 9. Final Checklist Before Any Change

Before making a change, confirm all of the following:

- [ ] I read `FileMap.md`.
- [ ] I understand the task goal and acceptance criteria.
- [ ] I checked current commit history and relevant diffs.
- [ ] I inspected the exact current file contents.
- [ ] I know the exact files the developer authorized me to change.
- [ ] Any related-file changes have been explicitly approved.
- [ ] I preserved comments and existing conventions.
- [ ] I did not invent assumptions or claim unverified results.
- [ ] I will report exactly what changed and what did not.

If any required context is missing, ask the developer before proceeding.
