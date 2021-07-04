# Rust (rust_analyzer)

https://github.com/rust-analyzer/rust-analyzer

rust-analyzer (aka rls 2.0), a language server for Rust

See [docs](https://github.com/rust-analyzer/rust-analyzer/tree/master/docs/user#settings) for extra settings.
    

## Setup

```lua
require'lspconfig'.rust_analyzer.setup{}
```

### Commands

- CargoReload: Reload current cargo workspace

### Default values

```lua
cmd = { "rust-analyzer" }
filetypes = { "rust" }
root_dir = root_pattern("Cargo.toml", "rust-project.json")
settings = {
  ["rust-analyzer"] = {}
}
```


This server accepts configuration via the `settings` key.

## Available settings

### `$generated-end`

  

 null

### `$generated-start`

  

 null

### `rust-analyzer.assist.allowMergingIntoGlobImports`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.assist.importEnforceGranularity`

  * *Type*: `boolean`

 null

### `rust-analyzer.assist.importGranularity`

  `enum { "preserve", "crate", "module", "item" }`

 * *Default*: `"crate"`
 
 null

### `rust-analyzer.assist.importGroup`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.assist.importPrefix`

  `enum { "plain", "self", "crate" }`

 * *Default*: `"plain"`
 
 null

### `rust-analyzer.callInfo.full`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.cargo.allFeatures`

  * *Type*: `boolean`

 null

### `rust-analyzer.cargo.autoreload`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.cargo.features`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 null

### `rust-analyzer.cargo.noDefaultFeatures`

  * *Type*: `boolean`

 null

### `rust-analyzer.cargo.noSysroot`

  * *Type*: `boolean`

 null

### `rust-analyzer.cargo.runBuildScripts`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.cargo.target`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null

### `rust-analyzer.cargo.unsetTest`

  * *Type*: `array`

 * *Default*: `{ "core" }`
 
 * *Array items*: `{type = "string"}`
 
 null

### `rust-analyzer.cargo.useRustcWrapperForBuildScripts`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.cargoRunner`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 Custom cargo runner extension ID\.

### `rust-analyzer.checkOnSave.allFeatures`

  * *Type*: `null|boolean`

 * *Default*: `vim.NIL`
 
 null

### `rust-analyzer.checkOnSave.allTargets`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.checkOnSave.command`

  * *Type*: `string`

 * *Default*: `"check"`
 
 null

### `rust-analyzer.checkOnSave.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.checkOnSave.extraArgs`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 null

### `rust-analyzer.checkOnSave.features`

  * *Type*: `null|array`

 * *Default*: `vim.NIL`
 
 * *Array items*: `{type = "string"}`
 
 null

### `rust-analyzer.checkOnSave.noDefaultFeatures`

  * *Type*: `null|boolean`

 * *Default*: `vim.NIL`
 
 null

### `rust-analyzer.checkOnSave.overrideCommand`

  * *Type*: `null|array`

 * *Default*: `vim.NIL`
 
 * *Array items*: `{type = "string"}`
 
 null

### `rust-analyzer.checkOnSave.target`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null

### `rust-analyzer.completion.addCallArgumentSnippets`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.completion.addCallParenthesis`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.completion.autoimport.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.completion.autoself.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.completion.postfix.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.debug.engine`

  `enum { "auto", "vadimcn.vscode-lldb", "ms-vscode.cpptools" }`

 * *Default*: `"auto"`
 
 Preferred debug engine\.

### `rust-analyzer.debug.engineSettings`

  * *Type*: `object`

 * *Default*: `vim.empty_dict()`
 
 null

### `rust-analyzer.debug.openDebugPane`

  * *Type*: `boolean`

 null

### `rust-analyzer.debug.sourceFileMap`

  * *Type*: `object|string`

 * *Default*: `{["/rustc/<id>"] = "${env:USERPROFILE}/.rustup/toolchains/<toolchain-id>/lib/rustlib/src/rust"}`
 
 Optional source file mappings passed to the debug engine\.

### `rust-analyzer.diagnostics.disabled`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 null

### `rust-analyzer.diagnostics.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.diagnostics.enableExperimental`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.diagnostics.remapPrefix`

  * *Type*: `object`

 * *Default*: `vim.empty_dict()`
 
 null

### `rust-analyzer.diagnostics.warningsAsHint`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 null

### `rust-analyzer.diagnostics.warningsAsInfo`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 null

### `rust-analyzer.experimental.procAttrMacros`

  * *Type*: `boolean`

 null

### `rust-analyzer.files.excludeDirs`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 null

### `rust-analyzer.files.watcher`

  * *Type*: `string`

 * *Default*: `"client"`
 
 null

### `rust-analyzer.highlighting.strings`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.hover.documentation`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.hover.linksInHover`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.hoverActions.debug`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.hoverActions.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.hoverActions.gotoTypeDef`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.hoverActions.implementations`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.hoverActions.references`

  * *Type*: `boolean`

 null

### `rust-analyzer.hoverActions.run`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.inlayHints.chainingHints`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.inlayHints.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to show inlay hints\.

### `rust-analyzer.inlayHints.maxLength`

  * *Type*: `null|integer`

 * *Default*: `25`
 
 null

### `rust-analyzer.inlayHints.parameterHints`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.inlayHints.smallerHints`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether inlay hints font size should be smaller than editor\'s font size\.

### `rust-analyzer.inlayHints.typeHints`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.lens.debug`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.lens.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.lens.implementations`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.lens.methodReferences`

  * *Type*: `boolean`

 null

### `rust-analyzer.lens.references`

  * *Type*: `boolean`

 null

### `rust-analyzer.lens.run`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.linkedProjects`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = { "string", "object" }}`
 
 null

### `rust-analyzer.lruCapacity`

  * *Type*: `null|integer`

 * *Default*: `vim.NIL`
 
 null

### `rust-analyzer.notifications.cargoTomlNotFound`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.procMacro.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `rust-analyzer.procMacro.server`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null

### `rust-analyzer.runnableEnv`

  

 * *Default*: `vim.NIL`
 
 null

### `rust-analyzer.runnables.cargoExtraArgs`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 null

### `rust-analyzer.runnables.overrideCargo`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null

### `rust-analyzer.rustcSource`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null

### `rust-analyzer.rustfmt.enableRangeFormatting`

  * *Type*: `boolean`

 null

### `rust-analyzer.rustfmt.extraArgs`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 null

### `rust-analyzer.rustfmt.overrideCommand`

  * *Type*: `null|array`

 * *Default*: `vim.NIL`
 
 * *Array items*: `{type = "string"}`
 
 null

### `rust-analyzer.server.extraEnv`

  * *Type*: `null|object`

 * *Default*: `vim.NIL`
 
 null

### `rust-analyzer.server.path`

  * *Type*: `null|string`

 * *Default*: `vim.NIL`
 
 null

### `rust-analyzer.trace.extension`

  * *Type*: `boolean`

 Enable logging of VS Code extensions itself\.

### `rust-analyzer.trace.server`

  `enum { "off", "messages", "verbose" }`

 * *Default*: `"off"`
 
 Trace requests to the rust\-analyzer \(this is usually overly verbose and not recommended for regular users\)\.

### `rust-analyzer.updates.askBeforeDownload`

  * *Type*: `boolean`

 Whether to ask for permission before downloading any files from the Internet\.

### `rust-analyzer.updates.channel`

  `enum { "stable", "nightly" }`

 * *Default*: `"stable"`
 
 null

### `rust-analyzer.workspace.symbol.search.kind`

  `enum { "only_types", "all_symbols" }`

 * *Default*: `"only_types"`
 
 null

### `rust-analyzer.workspace.symbol.search.scope`

  `enum { "workspace", "workspace_and_dependencies" }`

 * *Default*: `"workspace"`
 
 null



