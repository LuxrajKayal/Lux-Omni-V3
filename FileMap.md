# Lux Omni V3 — File Map

This map records the current repository structure. The PDF.js and pdf-lib vendor directories are summarized at their top level; each contains the upstream library files. As described in `site/vendor/README.md`, the vendor libraries are not currently integrated into Lux Omni's runtime.

```text
Lux-Omni-V3/
├── .github/
│   └── workflows/
│       └── pages.yml
├── FileMap.md
├── README.md
├── clipboard.html
├── dev-tools/
│   ├── README.md
│   └── remove-comments.js
├── docs/
│   ├── ARCHITECTURE.md
│   ├── BUILD_LOG.md
│   ├── CONTENT_ADAPTER_GUIDE.md
│   ├── MIGRATION_LOG.md
│   └── PROVIDER_GUIDE.md
├── privacy.html
└── site/
    ├── index.html
    ├── icons/
    │   ├── README.md
    │   ├── preview.html
    │   ├── docs/
    │   │   ├── 01-static-layered-nexus-logo-guide.md
    │   │   └── 02-animated-layered-nexus-loader-guide.md
    │   └── svg/
    │       ├── lux-omni-app-icon.svg
    │       ├── lux-omni-flat-symbol.svg
    │       ├── lux-omni-loader.svg
    │       ├── lux-omni-micro-icon.svg
    │       └── lux-omni-micro-spinner.svg
    ├── css/
    │   ├── foundation/
    │   │   ├── tokens.css
    │   │   ├── reset.css
    │   │   └── document.css
    │   ├── shell/
    │   │   ├── topbar/
    │   │   │   └── topbar.css
    │   │   ├── sidebar/
    │   │   │   └── sidebar.css
    │   │   ├── workspace/
    │   │   │   └── workspace-shell.css
    │   │   └── viewport/
    │   │       ├── viewport-layout.css
    │   │       ├── viewport-controls.css
    │   │       ├── minimized-dock.css
    │   │       └── replacement-dialog.css
    │   ├── features/
    │   │   ├── pdf-editor/
    │   │   │   ├── pdf-editor.css
    │   │   │   ├── pdf-toolbar.css
    │   │   │   ├── pdf-viewer.css
    │   │   │   ├── pdf-search.css
    │   │   │   ├── pdf-annotations.css
    │   │   │   └── pdf-motion.css
    │   │   ├── dropbox/
    │   │   │   ├── dropbox-topbar.css
    │   │   │   ├── dropbox-modal.css
    │   │   │   ├── dropbox-file-browser.css
    │   │   │   ├── dropbox-selection.css
    │   │   │   ├── dropbox-actions.css
    │   │   │   └── dropbox-motion.css
    │   │   ├── snipping-tool/
    │   │   │   ├── capture-panel.css
    │   │   │   ├── selection-overlay.css
    │   │   │   ├── editor-shell.css
    │   │   │   ├── editor-toolbar.css
    │   │   │   ├── canvas-workarea.css
    │   │   │   └── snipping-motion.css
    │   │   ├── temporary-log/
    │   │   │   └── temporary-log.css
    │   │   ├── youtube/
    │   │   │   └── youtube.css
    │   │   ├── markdown/
    │   │   │   ├── markdown-viewer.css
    │   │   │   ├── markdown-editor.css
    │   │   │   └── markdown-toolbar.css
    │   │   ├── images/
    │   │   │   ├── image-viewer.css
    │   │   │   └── image-toolbar.css
    │   │   └── clipboard/
    │   │       ├── clipboard-panel.css
    │   │       └── clipboard-toolbar.css
    │   ├── themes/
    │   │   ├── light.css
    │   │   └── dark.css
    │   └── responsive/
    │       └── application-responsive.css
    ├── js/
    │   ├── main.js
    │   ├── core/
    │   │   ├── AdapterRegistry.js
    │   │   ├── Constants.js
    │   │   ├── EventBus.js
    │   │   ├── ProviderRegistry.js
    │   │   ├── ServiceRegistry.js
    │   │   └── Store.js
    │   ├── models/
    │   │   ├── ProviderConfig.js
    │   │   ├── ProviderStatus.js
    │   │   ├── ViewportItem.js
    │   │   ├── WorkspaceFile.js
    │   │   └── WorkspaceState.js
    │   ├── providers/
    │   │   ├── shared/
    │   │   │   ├── AuthProvider.js
    │   │   │   ├── ProviderError.js
    │   │   │   ├── ProviderFactory.js
    │   │   │   ├── ProviderTypes.js
    │   │   │   ├── StorageAdapter.js
    │   │   │   └── SyncProvider.js
    │   │   ├── local/
    │   │   │   ├── LocalStorageAdapter.js
    │   │   │   ├── LocalFilePicker.js
    │   │   │   └── LocalDownload.js
    │   │   ├── dropbox/
    │   │   │   ├── DropboxApi.js
    │   │   │   ├── DropboxAuth.js
    │   │   │   ├── DropboxConfig.js
    │   │   │   ├── DropboxStorageAdapter.js
    │   │   │   └── DropboxSync.js
    │   │   ├── gdrive/
    │   │   │   ├── GoogleDriveApi.js
    │   │   │   ├── GoogleDriveAuth.js
    │   │   │   ├── GoogleDriveConfig.js
    │   │   │   ├── GoogleDriveStorageAdapter.js
    │   │   │   └── GoogleDriveSync.js
    │   │   ├── github/
    │   │   │   ├── GitHubApi.js
    │   │   │   ├── GitHubAuth.js
    │   │   │   ├── GitHubConfig.js
    │   │   │   ├── GitHubStorageAdapter.js
    │   │   │   └── GitHubSync.js
    │   │   ├── onedrive/
    │   │   │   ├── OneDriveApi.js
    │   │   │   ├── OneDriveAuth.js
    │   │   │   ├── OneDriveConfig.js
    │   │   │   ├── OneDriveStorageAdapter.js
    │   │   │   └── OneDriveSync.js
    │   │   └── s3/
    │   │       ├── S3Api.js
    │   │       ├── S3Auth.js
    │   │       ├── S3Config.js
    │   │       ├── S3StorageAdapter.js
    │   │       └── S3Sync.js
    │   ├── services/
    │   │   ├── CaptureService.js
    │   │   ├── ClipboardDb.js
    │   │   ├── ClipboardService.js
    │   │   ├── ConnectionManager.js
    │   │   ├── DownloadService.js
    │   │   ├── FileManager.js
    │   │   ├── ProviderManager.js
    │   │   └── SyncManager.js
    │   ├── adapters/
    │   │   └── content/
    │   │       ├── AdapterFactory.js
    │   │       ├── AudioAdapter.js
    │   │       ├── CsvAdapter.js
    │   │       ├── HtmlAdapter.js
    │   │       ├── ImageAdapter.js
    │   │       ├── JsonAdapter.js
    │   │       ├── MarkdownAdapter.js
    │   │       ├── PdfAdapter.js
    │   │       ├── TextAdapter.js
    │   │       ├── VideoAdapter.js
    │   │       └── YouTubeAdapter.js
    │   ├── viewport/
    │   │   ├── ViewportActions.js
    │   │   ├── ViewportController.js
    │   │   ├── ViewportHistory.js
    │   │   ├── ViewportLoader.js
    │   │   └── WorkspaceViewport.js
    │   ├── ui/
    │   │   ├── ConnectionBadgeUI.js
    │   │   ├── DropboxModalUI.js
    │   │   ├── FilePickerUI.js
    │   │   ├── GoogleDriveModalUI.js
    │   │   ├── OneDriveModalUI.js
    │   │   ├── ProviderMenuUI.js
    │   │   ├── ProviderStatusUI.js
    │   │   ├── SmartToolbarUI.js
    │   │   ├── SnippingEditorUI.js
    │   │   ├── ToastUI.js
    │   │   └── WorkspaceUI.js
    │   ├── state/
    │   │   ├── EditorState.js
    │   │   ├── ProviderState.js
    │   │   ├── SessionState.js
    │   │   └── WorkspaceState.js
    │   ├── storage/
    │   │   ├── CacheRepository.js
    │   │   ├── IndexedDbRepository.js
    │   │   ├── LocalStorageRepository.js
    │   │   └── SessionRepository.js
    │   └── utils/
    │       ├── FeatureFlags.js
    │       ├── FileClassifier.js
    │       ├── Helpers.js
    │       ├── Logger.js
    │       ├── MimeTypes.js
    │       ├── Security.js
    │       └── Validators.js
    └── vendor/
        ├── README.md
        ├── pdf-lib/
        │   └── Full upstream library tree (see directory)
        └── pdf.js/
            └── Full upstream library tree (see directory)
```

## Directory overview

- `.github/workflows/pages.yml` — GitHub Pages deployment workflow.
- `dev-tools/` — repository maintenance utilities.
- `docs/` — architecture, build history, migration, adapter, and provider documentation.
- `site/icons/` — Lux Omni icon assets, SVG variants, preview, and design guides.
- `site/css/` — foundation styles, application shell, feature styles, themes, and responsive rules.
- `site/js/core/` — application-wide registries, shared state, constants, and event bus.
- `site/js/models/` — application data models.
- `site/js/providers/` — local storage and cloud-provider adapters/authentication/sync modules.
- `site/js/services/` — file, connection, sync, download, capture, and clipboard services.
- `site/js/adapters/content/` — adapters for PDF, images, video, audio, Markdown, text, HTML, CSV, JSON, and YouTube content.
- `site/js/viewport/` and `site/js/ui/` — viewport behavior and user-interface modules.
- `site/js/state/` and `site/js/storage/` — state containers and persistence repositories.
- `site/vendor/` — vendored PDF.js and pdf-lib source trees, documented separately in `site/vendor/README.md`.

Note: `site/index.html` is listed as a repository path only; temporary testing or content mismatches in that file are outside the scope of this map update.
