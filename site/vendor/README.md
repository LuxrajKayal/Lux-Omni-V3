# Third-party libraries

## Current status

Neither library is currently used by Lux Omni. The repositories are vendored for evaluation only. No application imports, runtime loading, PDF viewing, PDF editing, or worker configuration has been implemented.

## Order of consideration

1. **PDF.js (Mozilla) — primary choice.** Evaluate first for PDF loading, parsing, rendering, and viewing inside Lux Omni.
2. **pdf-lib (Hopding) — optional secondary library.** Consider only if a required PDF creation or modification feature cannot be provided appropriately by the chosen PDF.js workflow.
3. **Remove what is not needed.** If pdf-lib proves unnecessary, delete  from Lux Omni. Its upstream repository remains available at the link below.

## Imported upstream snapshots

- PDF.js: https://github.com/mozilla/pdf.js — commit  — Apache-2.0
- pdf-lib: https://github.com/Hopding/pdf-lib — commit  — MIT

The library source files and upstream documentation are copied from the pinned upstream commits without application-specific edits. Git metadata is not included. Root library README and license files are preserved inside each library directory.

## Integration reminder

Having source code in this folder does **not** make either library active in the website. Select and configure suitable browser-ready build files and, for PDF.js, its matching worker before use. Do not wire either library into the app until implementation is explicitly planned and tested.
