# C like (sourcekit)

https://github.com/apple/sourcekit-lsp

Language server for Swift and C/C++/Objective-C.
    

## Setup

```lua
require'lspconfig'.sourcekit.setup{}
```


### Default values

```lua
cmd = { "xcrun", "sourcekit-lsp" }
filetypes = { "swift", "c", "cpp", "objective-c", "objective-cpp" }
root_dir = root_pattern("Package.swift", ".git")
```


This server accepts configuration via the `settings` key.

## Available settings

### `sourcekit-lsp.inlayHints.enabled`

  * *Type*: `boolean`

 \(experimental\) Render inlay type annotations in the editor\.

### `sourcekit-lsp.serverArguments`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 Arguments to pass to sourcekit\-lsp\. Argument keys and values should be provided as separate entries in the array e\.g\. \[\'\-\-log\-level\'\, \'debug\'\]

### `sourcekit-lsp.serverPath`

  * *Type*: `string`

 * *Default*: `"sourcekit-lsp"`
 
 The path of the sourcekit\-lsp executable

### `sourcekit-lsp.toolchainPath`

  * *Type*: `string`

 * *Default*: `""`
 
 \(optional\) The path of the swift toolchain\. By default\, sourcekit\-lsp uses the toolchain it is installed in\.

### `sourcekit-lsp.trace.server`

  `enum { "off", "messages", "verbose" }`

 * *Default*: `"off"`
 
 Traces the communication between VS Code and the SourceKit\-LSP language server\.



