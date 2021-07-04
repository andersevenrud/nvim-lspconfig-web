# Dart (dartls)

https://github.com/dart-lang/sdk/tree/master/pkg/analysis_server/tool/lsp_spec

Language server for dart.


## Setup

```lua
require'lspconfig'.dartls.setup{}
```


### Default values

```lua
cmd = { "dart", "/opt/dart-sdk/bin/snapshots/analysis_server.dart.snapshot", "--lsp" }
filetypes = { "dart" }
init_options = {
  closingLabels = false,
  flutterOutline = false,
  onlyAnalyzeProjectsWithOpenFiles = false,
  outline = false,
  suggestFromUnimportedLibraries = true
}
root_dir = root_pattern("pubspec.yaml")
```


This server accepts configuration via the `settings` key.

## Available settings

### `dart.additionalAnalyzerFileExtensions`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 Additional file extensions that should be analyzed \(usually used in combination with analyzer plugins\)\.

### `dart.allowAnalytics`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to send analytics such as startup timings\, frequency of use of features and analysis server crashes\.

### `dart.allowTestsOutsideTestFolder`

  * *Type*: `boolean`

 null

### `dart.analysisExcludedFolders`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 An array of paths to be excluded from Dart analysis\. This option should usually be set at the Workspace level\. Excluded folders will also be ignored when detecting project types\.

### `dart.analysisServerFolding`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to use folding data from the Dart analysis server instead of the built\-in VS Code indent\-based folding\.

### `dart.analyzeAngularTemplates`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `dart.analyzerAdditionalArgs`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 Additional arguments to pass to the Dart analysis server\.

### `dart.analyzerDiagnosticsPort`

  * *Type*: `null|number`

 * *Default*: `vim.NIL`
 
 The port number to be used for the Dart analyzer diagnostic server\.

### `dart.analyzerInstrumentationLogFile`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 The path to a log file for very detailed logging in the Dart analysis server that may be useful when trying to diagnose analysis server issues\.

### `dart.analyzerLogFile`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 The path to a log file for communication between Dart Code and the analysis server\.

### `dart.analyzerPath`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 The path to a custom Dart analysis server\.

### `dart.analyzerSshHost`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 An SSH host to run the analysis server\.
 This can be useful when modifying code on a remote machine using SSHFS\.

### `dart.analyzerVmServicePort`

  * *Type*: `null|number`

 * *Default*: `vim.NIL`
 
 The port number to be used for the Dart analysis server VM service\.

### `dart.autoImportCompletions`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to include symbols that have not been imported in the code completion list and automatically insert the required import when selecting them \(requires restart\)\.

### `dart.automaticCommentSlashes`

  `enum { "none", "tripleSlash", "all" }`

 * *Default*: `"tripleSlash"`
 
 null

### `dart.buildRunnerAdditionalArgs`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 null

### `dart.checkForSdkUpdates`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to check you are using the latest version of the Dart SDK at startup\.

### `dart.cliConsole`

  `enum { "debugConsole", "terminal", "externalTerminal" }`

 * *Default*: `"debugConsole"`
 
 Whether to run Dart CLI apps in the Debug Console or a terminal\. The Debug Console has more functionality because the process is controlled by the debug adapter\, but is unable to accept input from the user via stdin\.

### `dart.closingLabels`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to show annotations against constructor\, method invocations and lists that span multiple lines\.

### `dart.completeFunctionCalls`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `dart.dapLogFile`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null

### `dart.debugExtensionBackendProtocol`

  `enum { "sse", "ws" }`

 * *Default*: `"ws"`
 
 The protocol to use for the Dart Debug Extension backend service and injected client\. Using WebSockets can improve performance but may fail when connecting through some proxy servers\.

### `dart.debugExternalLibraries`

  * *Type*: `boolean`

 null

### `dart.debugSdkLibraries`

  * *Type*: `boolean`

 null

### `dart.devToolsBrowser`

  `enum { "chrome", "default" }`

 * *Default*: `"chrome"`
 
 Whether to launch external DevTools windows using Chrome or the system default browser\.

### `dart.devToolsLogFile`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 The path to a low\-traffic log file for the Dart DevTools service\.

### `dart.devToolsPort`

  * *Type*: `null|number`

 * *Default*: `vim.NIL`
 
 The port number to be used for the Dart DevTools\.

### `dart.devToolsReuseWindows`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to try to reuse existing DevTools windows instead of launching new ones\. Only works for instances of DevTools launched by the DevTools server on the local machine\.

### `dart.devToolsTheme`

  `enum { "dark", "light" }`

 * *Default*: `"dark"`
 
 The theme to use for Dart DevTools\.

### `dart.doNotFormat`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 null

### `dart.embedDevTools`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `dart.enableCompletionCommitCharacters`

  * *Type*: `boolean`

 null

### `dart.enableSdkFormatter`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `dart.enableServerSnippets`

  * *Type*: `boolean`

 null

### `dart.enableSnippets`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to include Dart and Flutter snippets in code completion\.

### `dart.env`

  * *Type*: `object`

 * *Default*: `vim.empty_dict()`
 
 Additional environment variables to be added to all Dart\/Flutter processes spawned by the Dart and Flutter extensions\.

### `dart.evaluateGettersInDebugViews`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to evaluate getters in order to display them in debug views \(such as the Variables\, Watch and Hovers views\)\.

### `dart.evaluateToStringInDebugViews`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to call toString\(\) on objects when rendering them in debug views \(such as the Variables\, Watch and Hovers views\)\. Only applies to views of 100 or fewer values for performance reasons\.

### `dart.extensionLogFile`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 The path to a low\-traffic log file for basic extension and editor issues\.

### `dart.flutterAdbConnectOnChromeOs`

  * *Type*: `boolean`

 null

### `dart.flutterAdditionalArgs`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 null

### `dart.flutterAttachAdditionalArgs`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 null

### `dart.flutterCreateAndroidLanguage`

  `enum { "java", "kotlin" }`

 * *Default*: `"kotlin"`
 
 The programming language to use for Android apps when creating new projects using the \'Flutter\: New Application Project\' command\.

### `dart.flutterCreateIOSLanguage`

  `enum { "objc", "swift" }`

 * *Default*: `"swift"`
 
 The programming language to use for iOS apps when creating new projects using the \'Flutter\: New Application Project\' command\.

### `dart.flutterCreateOffline`

  * *Type*: `boolean`

 Whether to use offline mode when creating new projects with the \'Flutter\: New Application Project\' command\.

### `dart.flutterCreateOrganization`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null

### `dart.flutterCustomEmulators`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{properties = {args = {items = {type = "string"},type = "array"},env = vim.empty_dict(),executable = {type = "string"},id = {type = "string"},name = {type = "string"}},type = "object"}`
 
 Custom emulators to show in the emulator list for easier launching\. If IDs match existing emulators returned by Flutter\, the custom emulators will override them\.

### `dart.flutterDaemonLogFile`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null

### `dart.flutterGutterIcons`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to show Flutter icons and colors in the editor gutter\.

### `dart.flutterHotReloadOnSave`

  `enum { "never", "always", "manual" }`

 * *Default*: `"manual"`
 
 null

### `dart.flutterHotRestartOnSave`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to automatically send a Hot Restart request during a debug session when saving files if Hot Reload is not available but Hot Restart is\.

### `dart.flutterOutline`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to show the Flutter Outline tree in the sidebar\.

### `dart.flutterRunAdditionalArgs`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 null

### `dart.flutterRunLogFile`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null

### `dart.flutterScreenshotPath`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 The path to a directory to save Flutter screenshots\.

### `dart.flutterSdkPath`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null

### `dart.flutterSdkPaths`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 An array of paths that either directly point to a Flutter SDK or the parent directory of multiple Flutter SDKs\. When set\, the version number in the status bar can be used to quickly switch between SDKs\.

### `dart.flutterSelectDeviceWhenConnected`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to set newly connected devices as the current device in Flutter projects\.

### `dart.flutterShowEmulators`

  `enum { "local", "always" }`

 * *Default*: `"local"`
 
 null

### `dart.flutterShowWebServerDevice`

  `enum { "remote", "always" }`

 * *Default*: `"remote"`
 
 null

### `dart.flutterStructuredErrors`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `dart.flutterTestAdditionalArgs`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 null

### `dart.flutterTestLogFile`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null

### `dart.flutterTrackWidgetCreation`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `dart.flutterWebRenderer`

  `enum { "auto", "html", "canvaskit" }`

 * *Default*: `"auto"`
 
 null

### `dart.hotReloadProgress`

  `enum { "notification", "statusBar" }`

 * *Default*: `"notification"`
 
 Determines how to display Hot Restart and Hot Reload progress\.

### `dart.insertArgumentPlaceholders`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `dart.lineLength`

  * *Type*: `integer`

 * *Default*: `80`
 
 The maximum length of a line of code\. This is used by the document formatter\.

### `dart.lspSnippetTextEdits`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `dart.maxLogLineLength`

  * *Type*: `number`

 * *Default*: `2000`
 
 The maximum length of a line in the log file\. Lines longer than this will be truncated and suffixed with an ellipsis\.

### `dart.notifyAnalyzerErrors`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to show a notification the first few times an analysis server exception occurs\.

### `dart.openDevTools`

  `enum { "never", "flutter", "always" }`

 * *Default*: `"never"`
 
 Whether to automatically open DevTools at the start of a debug session\. If embedded DevTools is enabled\, this will launch the Widget Inspector embedded for Flutter projects\, or launch DevTools externally in a browser for Dart projects\.

### `dart.openTestView`

  * *Type*: `array`

 * *Default*: `{ "testRunStart" }`
 
 * *Array items*: `{enum = { "testRunStart", "testFailure" }}`
 
 When to automatically switch focus to the test list \(array to support multiple values\)\.

### `dart.previewBazelWorkspaceCustomScripts`

  * *Type*: `boolean`

 null

### `dart.previewCommitCharacters`

  * *Type*: `boolean`

 EXPERIMENTAL\: Whether to enable commit characters for the LSP server\. In a future release\, the dart\.enableCompletionCommitCharacters setting will also apply to LSP\.

### `dart.previewFlutterUiGuides`

  * *Type*: `boolean`

 null

### `dart.previewFlutterUiGuidesCustomTracking`

  * *Type*: `boolean`

 EXPERIMENTAL\: Whether to enable custom tracking of Flutter UI guidelines \(to hide some latency of waiting for the next Flutter Outline\)\.

### `dart.previewHotReloadOnSaveWatcher`

  * *Type*: `boolean`

 null

### `dart.previewLsp`

  * *Type*: `null|boolean`

 * *Default*: `vim.NIL`
 
 null

### `dart.promptToGetPackages`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to prompt to get packages when opening a project with out of date packages\.

### `dart.promptToRunIfErrors`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to prompt before running if there are errors in your project\. Test scripts will be excluded from the check unless they\'re the script being run\.

### `dart.pubAdditionalArgs`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 Additional args to pass to all \`pub\` commands\.

### `dart.pubTestLogFile`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null

### `dart.runPubGetOnPubspecChanges`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `dart.sdkPath`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null

### `dart.sdkPaths`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 An array of paths that either directly point to a Dart SDK or the parent directory of multiple Dart SDKs\. When set\, the version number in the status bar can be used to quickly switch between SDKs\.

### `dart.shareDevToolsWithFlutter`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to eagerly run DevTools for Flutter workspaces and share the spawned server with \`flutter run\`\.

### `dart.showDartDeveloperLogs`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `dart.showDartPadSampleCodeLens`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to show CodeLens actions in the editor for opening online DartPad samples\.

### `dart.showDevToolsDebugToolBarButtons`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to show DevTools buttons in the Debug toolbar\.

### `dart.showIgnoreQuickFixes`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to show quick fixes for ignoring hints and lints\.

### `dart.showInspectorNotificationsForWidgetErrors`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `dart.showMainCodeLens`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to show CodeLens actions in the editor for quick running \/ debugging scripts with main functions\.

### `dart.showSkippedTests`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `dart.showTestCodeLens`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to show CodeLens actions in the editor for quick running \/ debugging tests\.

### `dart.showTodos`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to show TODOs in the Problems list\.

### `dart.triggerSignatureHelpAutomatically`

  * *Type*: `boolean`

 Whether to automatically trigger signature help when pressing keys such as \, and \(\.

### `dart.updateImportsOnRename`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to automatically update imports when moving or renaming files\. Currently only supports single file moves \/ renames\.

### `dart.useKnownChromeOSPorts`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to use specific ports for the VM service and DevTools when running in Chrome OS\. This is required to connect from the native Chrome OS browser but will prevent apps from launching if the ports are already in\-use \(for example if trying to run a second app\)\.

### `dart.vmAdditionalArgs`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 Additional args to pass to the Dart VM when running\/debugging command line apps\.

### `dart.vmServiceLogFile`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null

### `dart.warnWhenEditingFilesInPubCache`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `dart.warnWhenEditingFilesOutsideWorkspace`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to show a warning when modifying files outside of the workspace\.

### `dart.webDaemonLogFile`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null



