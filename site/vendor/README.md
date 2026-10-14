# Third-party libraries

## Current status

**Neither library is currently used by Lux Omni.** These repositories are included for evaluation only. No application imports, runtime loading, PDF viewing, PDF editing, or worker configuration has been implemented.

## Order of consideration

1. **PDF.js (Mozilla) — primary choice.** Evaluate it first for PDF loading, parsing, rendering, and viewing inside Lux Omni.
2. **pdf-lib (Hopding) — optional secondary library.** Consider it only if a required PDF creation or modification feature cannot be provided appropriately by the chosen PDF.js workflow.
3. **Remove what is not needed.** If evaluation shows pdf-lib is unnecessary, remove the `site/vendor/pdf-lib` submodule entry and its matching section from `.gitmodules`. Do not delete source files from either upstream project; remove the submodule link from this project instead.

## Repositories

- PDF.js: https://github.com/mozilla/pdf.js.git
  - Pinned upstream commit: `fcde2e1f9a960e9d234caea43746d6223cd054df`
  - License: Apache-2.0
- pdf-lib: https://github.com/Hopding/pdf-lib.git
  - Pinned upstream commit: `93dd36e85aa659a3bca09867d2d8fac172501fbe`
  - License: MIT

The library directories are Git submodules so their upstream source stays separate and unmodified. The parent Lux Omni repository records each pinned upstream commit.

## Checkout

Clone this project with submodules:

```sh
git clone --recurse-submodules https://github.com/LuxrajKayal/Lux-Omni-V3.git
```

For an existing clone:

```sh
git submodule update --init --recursive
```

## Integration reminder

Having the source repositories here does **not** make the libraries active in the website. Before use, select and configure suitable browser-ready distribution/build files and, for PDF.js, its matching worker. Do not wire either library into the app until implementation is explicitly planned and tested.
