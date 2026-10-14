Lux-Omni/
│
├── .github/
│   └── workflows/
│       └── pages.yml
│
├── docs/
│   ├── ARCHITECTURE.md
│   ├── PROVIDER_GUIDE.md
│   ├── CONTENT_ADAPTER_GUIDE.md
│   └── MIGRATION_LOG.md
│
├── dev-tools/
│   ├── README.md
│   └── remove-comments.js
│
├── clipboard.html
├── privacy.html
│
└── site/
    │
    ├── index.html
    ├── styles.css
    │
    ├── icons/
    │   ├── lux-pdf-viewer-icon.svg
    │   ├── lux-pdf-viewer-icon-64.png
    │   └── lux-pdf-viewer-icon-256.png
    │
    ├── components/
    │   ├── pdf-editor.css
    │   ├── snipping-tool.css
    │   ├── dropbox-ui.css
    │   └── temporary-log.css
    │
    └── js/
        │
        ├── main.js
        │
        ├── core/
        │   │
        │   ├── EventBus.js
        │   ├── Store.js
        │   ├── AdapterRegistry.js
        │   ├── ServiceRegistry.js
        │   ├── ProviderRegistry.js
        │   └── Constants.js
        │
        ├── models/
        │   │
        │   ├── WorkspaceFile.js
        │   ├── WorkspaceState.js
        │   ├── ProviderStatus.js
        │   ├── ProviderConfig.js
        │   └── ViewportItem.js
        │
        ├── providers/
        │   │
        │   ├── shared/
        │   │   │
        │   │   ├── StorageAdapter.js
        │   │   ├── AuthProvider.js
        │   │   ├── SyncProvider.js
        │   │   ├── ProviderFactory.js
        │   │   ├── ProviderTypes.js
        │   │   └── ProviderError.js
        │   │
        │   ├── local/
        │   │   │
        │   │   ├── LocalStorageAdapter.js
        │   │   ├── LocalFilePicker.js
        │   │   └── LocalDownload.js
        │   │
        │   ├── dropbox/
        │   │   │
        │   │   ├── DropboxApi.js
        │   │   ├── DropboxAuth.js
        │   │   ├── DropboxStorageAdapter.js
        │   │   ├── DropboxSync.js
        │   │   └── DropboxConfig.js
        │   │
        │   ├── gdrive/
        │   │   │
        │   │   ├── GoogleDriveApi.js
        │   │   ├── GoogleDriveAuth.js
        │   │   ├── GoogleDriveStorageAdapter.js
        │   │   ├── GoogleDriveSync.js
        │   │   └── GoogleDriveConfig.js
        │   │
        │   ├── onedrive/
        │   │   │
        │   │   ├── OneDriveApi.js
        │   │   ├── OneDriveAuth.js
        │   │   ├── OneDriveStorageAdapter.js
        │   │   ├── OneDriveSync.js
        │   │   └── OneDriveConfig.js
        │   │
        │   ├── github/
        │   │   │
        │   │   ├── GitHubApi.js
        │   │   ├── GitHubAuth.js
        │   │   ├── GitHubStorageAdapter.js
        │   │   ├── GitHubSync.js
        │   │   └── GitHubConfig.js
        │   │
        │   └── s3/
        │       │
        │       ├── S3Api.js
        │       ├── S3Auth.js
        │       ├── S3StorageAdapter.js
        │       ├── S3Sync.js
        │       └── S3Config.js
        │
        ├── services/
        │   │
        │   ├── FileManager.js
        │   ├── ConnectionManager.js
        │   ├── SyncManager.js
        │   ├── ProviderManager.js
        │   ├── DownloadService.js
        │   │
        │   ├── CaptureService.js
        │   ├── ClipboardDb.js
        │   └── ClipboardService.js
        │
        ├── adapters/
        │   │
        │   └── content/
        │       │
        │       ├── AdapterFactory.js
        │       │
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
        │
        ├── viewport/
        │   │
        │   ├── WorkspaceViewport.js
        │   ├── ViewportController.js
        │   ├── ViewportLoader.js
        │   ├── ViewportHistory.js
        │   └── ViewportActions.js
        │
        ├── ui/
        │   │
        │   ├── WorkspaceUI.js
        │   ├── SmartToolbarUI.js
        │   ├── ToastUI.js
        │   ├── SnippingEditorUI.js
        │   │
        │   ├── FilePickerUI.js
        │   ├── ProviderMenuUI.js
        │   ├── ProviderStatusUI.js
        │   ├── ConnectionBadgeUI.js
        │   │
        │   ├── DropboxModalUI.js
        │   ├── GoogleDriveModalUI.js
        │   └── OneDriveModalUI.js
        │
        ├── state/
        │   │
        │   ├── WorkspaceState.js
        │   ├── ProviderState.js
        │   ├── SessionState.js
        │   └── EditorState.js
        │
        ├── storage/
        │   │
        │   ├── IndexedDbRepository.js
        │   ├── LocalStorageRepository.js
        │   ├── SessionRepository.js
        │   └── CacheRepository.js
        │
        └── utils/
            │
            ├── FileClassifier.js
            ├── MimeTypes.js
            ├── Validators.js
            ├── Security.js
            ├── Logger.js
            ├── Helpers.js
            └── FeatureFlags.js