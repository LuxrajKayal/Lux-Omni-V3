Lux-Omni-V3/
├── .github/
│   └── workflows/
│       └── pages.yml
├── docs/
│   ├── ARCHITECTURE.md
│   ├── PROVIDER_GUIDE.md
│   ├── CONTENT_ADAPTER_GUIDE.md
│   └── MIGRATION_LOG.md
├── dev-tools/
│   ├── README.md
│   └── remove-comments.js
├── clipboard.html
├── privacy.html
└── site/
    ├── index.html
    ├── icons/
    │   ├── lux-pdf-viewer-icon.svg
    │   ├── lux-pdf-viewer-icon-64.png
    │   └── lux-pdf-viewer-icon-256.png
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
    └── js/
        ├── main.js
        ├── core/
        │   ├── EventBus.js
        │   ├── Store.js
        │   ├── AdapterRegistry.js
        │   ├── ServiceRegistry.js
        │   ├── ProviderRegistry.js
        │   └── Constants.js
        ├── models/
        │   ├── WorkspaceFile.js
        │   ├── WorkspaceState.js
        │   ├── ProviderStatus.js
        │   ├── ProviderConfig.js
        │   └── ViewportItem.js
        ├── providers/
        │   ├── shared/
        │   │   ├── StorageAdapter.js
        │   │   ├── AuthProvider.js
        │   │   ├── SyncProvider.js
        │   │   ├── ProviderFactory.js
        │   │   ├── ProviderTypes.js
        │   │   └── ProviderError.js
        │   ├── local/
        │   │   ├── LocalStorageAdapter.js
        │   │   ├── LocalFilePicker.js
        │   │   └── LocalDownload.js
        │   ├── dropbox/
        │   │   ├── DropboxApi.js
        │   │   ├── DropboxAuth.js
        │   │   ├── DropboxStorageAdapter.js
        │   │   ├── DropboxSync.js
        │   │   └── DropboxConfig.js
        │   ├── gdrive/
        │   │   ├── GoogleDriveApi.js
        │   │   ├── GoogleDriveAuth.js
        │   │   ├── GoogleDriveStorageAdapter.js
        │   │   ├── GoogleDriveSync.js
        │   │   └── GoogleDriveConfig.js
        │   ├── onedrive/
        │   │   ├── OneDriveApi.js
        │   │   ├── OneDriveAuth.js
        │   │   ├── OneDriveStorageAdapter.js
        │   │   ├── OneDriveSync.js
        │   │   └── OneDriveConfig.js
        │   ├── github/
        │   │   ├── GitHubApi.js
        │   │   ├── GitHubAuth.js
        │   │   ├── GitHubStorageAdapter.js
        │   │   ├── GitHubSync.js
        │   │   └── GitHubConfig.js
        │   └── s3/
        │       ├── S3Api.js
        │       ├── S3Auth.js
        │       ├── S3StorageAdapter.js
        │       ├── S3Sync.js
        │       └── S3Config.js
        ├── services/
        │   ├── FileManager.js
        │   ├── ConnectionManager.js
        │   ├── SyncManager.js
        │   ├── ProviderManager.js
        │   ├── DownloadService.js
        │   ├── CaptureService.js
        │   ├── ClipboardDb.js
        │   └── ClipboardService.js
        ├── adapters/
        │   └── content/
        │       ├── AdapterFactory.js
        │       ├── PdfAdapter.js
        │       ├── ImageAdapter.js
        │       ├── VideoAdapter.js
        │       ├── AudioAdapter.js
        │       ├── MarkdownAdapter.js
        │       ├── TextAdapter.js
        │       ├── HtmlAdapter.js
        │       ├── CsvAdapter.js
        │       ├── JsonAdapter.js
        │       └── YouTubeAdapter.js
        ├── viewport/
        │   ├── WorkspaceViewport.js
        │   ├── ViewportController.js
        │   ├── ViewportLoader.js
        │   ├── ViewportHistory.js
        │   └── ViewportActions.js
        ├── ui/
        │   ├── WorkspaceUI.js
        │   ├── SmartToolbarUI.js
        │   ├── ToastUI.js
        │   ├── SnippingEditorUI.js
        │   ├── FilePickerUI.js
        │   ├── ProviderMenuUI.js
        │   ├── ProviderStatusUI.js
        │   ├── ConnectionBadgeUI.js
        │   ├── DropboxModalUI.js
        │   ├── GoogleDriveModalUI.js
        │   └── OneDriveModalUI.js
        ├── state/
        │   ├── WorkspaceState.js
        │   ├── ProviderState.js
        │   ├── SessionState.js
        │   └── EditorState.js
        ├── storage/
        │   ├── IndexedDbRepository.js
        │   ├── LocalStorageRepository.js
        │   ├── SessionRepository.js
        │   └── CacheRepository.js
        └── utils/
            ├── FileClassifier.js
            ├── MimeTypes.js
            ├── Validators.js
            ├── Security.js
            ├── Logger.js
            ├── Helpers.js
            └── FeatureFlags.js
