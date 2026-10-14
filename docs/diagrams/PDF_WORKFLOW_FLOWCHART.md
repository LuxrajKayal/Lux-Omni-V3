# Lux Omni PDF Workflow

> **Status: architecture plan only.** PDF.js and pdf-lib are vendored under `site/vendor/`, but neither is currently imported or used by Lux Omni. The application adapter files are placeholders. This diagram describes the intended flow, not implemented behavior.

## Flowchart

```mermaid
flowchart TD
    A([User selects a PDF]) --> B[Acquire file bytes<br/>Local file picker or configured provider]
    B --> C[FileManager<br/>Validate type and retain source bytes]
    C --> D[ViewportLoader<br/>Classify as PDF]
    D --> E[PdfAdapter<br/>Integration boundary — planned]
    E --> F[PDF.js browser distribution<br/>and matching worker]
    F --> G[Parse and render pages]
    G --> H[Workspace viewport<br/>Canvas, text/search layer, page controls]
    H --> I{Must the actual PDF bytes<br/>be changed programmatically?}

    I -- No --> J[Keep the original bytes<br/>Store app state separately if needed]
    I -- Yes --> K[Evaluate the exact operation<br/>against pdf-lib capabilities]
    K --> L{Is pdf-lib suitable<br/>for that operation?}
    L -- No --> M[Reassess the requirement<br/>Do not claim unsupported save behavior]
    L -- Yes --> N[Apply supported change<br/>Export updated PDF bytes]
    N --> O[Reopen exported bytes in PDF.js<br/>and verify the result]

    J --> P[Save or download path]
    O --> P
    P --> Q[DownloadService or configured<br/>storage-provider integration]
    
    R[Do not add pdf-lib to runtime<br/>if the required feature does not need it] -. optional decision .-> I
```

## Responsibilities

- **PDF.js first:** use its browser build and its matching worker for PDF parsing, page rendering, and viewing.
- **pdf-lib only when justified:** consider it for specific PDF creation/modification operations. It is not a PDF renderer, and it must not be assumed to support every editing feature.
- **Preserve source bytes:** loading a PDF for viewing should not silently overwrite the user's original document.
- **Verify writes:** whenever bytes are modified, reopen the exported document and test the required pages, annotations, forms, or content before presenting the save as successful.
- **Keep storage separate:** local download and cloud sync are separate integration responsibilities. Do not imply any provider is connected unless it has actually been configured and tested.

## Engineering block diagram

![Lux Omni PDF engineering block diagram](./LUX_OMNI_PDF_ENGINEERING.svg)

## Implementation gate

Before runtime integration, select the browser-ready PDF.js build, include the matching worker, define the `PdfAdapter` contract, and test one representative PDF from open through render. Only then decide whether any required write operation warrants pdf-lib.
