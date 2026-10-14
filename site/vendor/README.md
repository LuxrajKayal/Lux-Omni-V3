# Third-party libraries

## Current status

Neither library is currently used by Lux Omni. The complete upstream repositories are stored here for evaluation only. No application imports, runtime loading, PDF viewing, PDF editing, or worker configuration has been implemented.

## Order of consideration

1. **PDF.js (Mozilla) — primary choice.** Evaluate first for PDF loading, parsing, rendering, and viewing inside Lux Omni.
2. **pdf-lib (Hopding) — optional secondary library.** Consider only if a required PDF creation or modification feature cannot be provided appropriately by the chosen PDF.js workflow.
3. **Remove what is not needed.** If pdf-lib proves unnecessary, delete `site/vendor/pdf-lib/` from Lux Omni. Its upstream repository remains available at the link below.

## Imported upstream snapshots

- PDF.js: https://github.com/mozilla/pdf.js — commit `fcde2e1f9a960e9d234caea43746d6223cd054df` — Apache-2.0
- pdf-lib: https://github.com/Hopding/pdf-lib — commit `93dd36e85aa659a3bca09867d2d8fac172501fbe` — MIT

The library source files and upstream documentation are copied from the pinned upstream commits without application-specific edits. Git metadata is not included. Each library's own README and license files are preserved inside its directory.

## Integration reminder

Having source code in this folder does **not** make either library active in the website. Select and configure suitable browser-ready build files and, for PDF.js, its matching worker before use. Do not wire either library into the app until implementation is explicitly planned and tested.
