# Lux Omni Workspace V3 — Project Status

> **Purpose:** A concise snapshot for the developer and future AI assistants. Read `instruction-for-chatbots.md` first and verify this page against the live repository before relying on it.

- **Last status review:** 2026-10-17
- **Repository:** [LuxrajKayal/Lux-Omni-V3](https://github.com/LuxrajKayal/Lux-Omni-V3)
- **Branch reviewed:** `main`
- **Baseline revision reviewed before this status file was created:** `f1607456f114f7ca553a449ed02f72589fa7c96e` — docs: record visual foundation progress and append-only log rules
- **Development stage:** Early skeleton with initial design-system and topbar styling underway.
- **Current working area:** CSS foundation, brand typography, and topbar learning.

---

## 1. Project Direction

Lux Omni Workspace V3 is intended to grow into a modular, multi-content workspace. The current file map outlines planned areas for a workspace shell, viewports, PDF viewing and editing, Markdown, images, YouTube, clipboard, capture/snipping tools, temporary logs, local files, and cloud-provider adapters.

This describes the intended product direction. It does **not** mean that every feature or every scaffolded module is implemented.

## 2. Developer's Current Focus

The developer is learning to style the topbar manually, step by step, and wants to understand the code before moving forward.

**Immediate learning task:** Continue learning the brand typography tokens in `site/css/foundation/typography.css` one at a time, then trace how `site/css/shell/topbar/topbar.css` consumes them. Explain each concept and let the developer confirm before moving on.

Do not take over the implementation or make edits while the developer is asking to learn, inspect, explain, or review. Repository changes require explicit permission for the exact scope.

## 3. Current Verified Implementation

### Design tokens and typography

- `site/css/foundation/tokens.css` defines Lux brand color primitives, grayscale values, reusable gradients, font-family tokens, and motion values.
- `site/css/foundation/typography.css` applies the shared sans-serif token to the body and common form controls, uses the monospace token for code-related elements, and defines brand name/slogan typography tokens.
- `site/css/themes/light.css` and `site/css/themes/dark.css` define theme-specific topbar background, main text, and muted text variables.

### Topbar and branding

- `site/index.html` contains the topbar structure, the brand icon, the visible name **Lux Omni Workspace**, the slogan, and the service-connection menu markup for Google Drive, Dropbox, and OneDrive.
- The root HTML element currently declares `data-theme="dark"`.
- `site/css/shell/topbar/topbar.css` includes the fixed topbar layout, the brand link layout, the 40-by-40-pixel logo container, the image sizing rule, and styles for the brand-copy stack, brand name, and slogan.
- The topbar stylesheet includes CSS for the overall shell and brand identity; the existence of markup for a connection menu does not by itself mean its interaction is implemented.

**Verification limit:** Source files and commit history were inspected. This status does not claim that a fresh browser-based visual or interaction test was run.

## 4. Not Yet Implemented or Not Yet Verified

- A working light/dark theme-toggle button.
- Persistence of a user's theme choice across reloads.
- Completed topbar connection-menu behavior and provider actions.
- Responsive behavior and cross-device visual verification for the topbar.
- The complete workspace shell and its document/viewport interactions.
- Runtime integration of PDF.js, including the correct browser build and matching worker.
- PDF editing, annotation, save/export, and other planned content-feature workflows.

Treat these as pending until code and tests confirm otherwise. A file listed in `FileMap.md` may be an empty placeholder.

## 5. Third-Party PDF Libraries

- Mozilla PDF.js is vendored in `site/vendor/pdf.js/`.
- pdf-lib is vendored in `site/vendor/pdf-lib/`.
- `site/vendor/README.md` records their upstream revisions and states that neither library was integrated into the application runtime at the time of its last documented update.
- The build log records upstream tree verification. Re-check the current runtime before making any later claim about integration.
- Do not modify vendored source without explicit permission.

## 6. Documentation Timing — Developer Decision

The developer has explicitly decided to defer final public-facing project documentation while the product is still in the skeleton stage.

1. **Do not write or edit the root `README.md` now.** The developer will author it at the end, after the product has progressed from the skeleton into a working implementation.
2. **Do not create or edit the root project `LICENSE` now.** The developer plans to author it after the README, when the project begins to take working shape.
3. This decision does not authorize edits to these files or any other file.
4. Preserve the upstream license and other legal files inside the vendored third-party libraries.

The current root `README.md` is only a minimal placeholder. Leave it untouched until the developer explicitly requests the final writing stage.

## 7. Next Suggested Milestones

These are recommendations, not permission to implement them:

1. Continue learning the typography tokens and the matching `.brand-name` / `.brand-slogan` rules.
2. Manually verify the topbar's appearance, then inspect any issues before changing CSS.
3. Finish the theme-token understanding and later implement the theme toggle and persistence with explicit approval.
4. Complete and test the shell before beginning PDF.js runtime integration.
5. Keep the build log accurate by appending dated, verified entries only when an update is authorized.

## 8. Update Discipline

- Treat this file as a current-state snapshot, not as a historical log.
- Update it only with developer authorization and only after checking the live repository.
- Do not mark tasks complete without verification.
- Keep the append-only `docs/BUILD_LOG.md` separate: its previous entries must never be removed or rewritten.
- Refresh this status when a meaningful milestone changes what is implemented, what is pending, or where the developer is currently working.

