# Fortan (fortls)

https://github.com/hansec/fortran-language-server

Fortran Language Server for the Language Server Protocol
    

## Setup

```lua
require'lspconfig'.fortls.setup{}
```


### Default values

```lua
cmd = { "fortls" }
filetypes = { "fortran" }
root_dir = root_pattern(".fortls")
settings = {
  nthreads = 1
}
```


This server accepts configuration via the `settings` key.

## Available settings

### `fortran-ls.autocompletePrefix`

  * *Type*: `boolean`

 Filter autocomplete suggestions with variable prefix

### `fortran-ls.disableDiagnostics`

  * *Type*: `boolean`

 Disable diagnostics \(requires v1\.12\.0+\)\.

### `fortran-ls.displayVerWarning`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Provides notifications when the underlying language server is out of date\.

### `fortran-ls.enableCodeActions`

  * *Type*: `boolean`

 Enable experimental code actions \(requires v1\.7\.0+\)\.

### `fortran-ls.executablePath`

  * *Type*: `string`

 * *Default*: `"fortls"`
 
 Path to the Fortran language server \(fortls\)\.

### `fortran-ls.hoverSignature`

  * *Type*: `boolean`

 Show signature information in hover for argument \(also enables \'variableHover\'\)\.

### `fortran-ls.includeSymbolMem`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Include type members in document outline \(also used for \'Go to Symbol in File\'\)

### `fortran-ls.incrementalSync`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Use incremental synchronization for file changes\.

### `fortran-ls.lowercaseIntrinsics`

  * *Type*: `boolean`

 Use lowercase for intrinsics and keywords in autocomplete requests\.

### `fortran-ls.maxCommentLineLength`

  * *Type*: `number`

 * *Default*: `-1`
 
 Maximum comment line length \(requires v1\.8\.0+\)\.

### `fortran-ls.maxLineLength`

  * *Type*: `number`

 * *Default*: `-1`
 
 Maximum line length \(requires v1\.8\.0+\)\.

### `fortran-ls.notifyInit`

  * *Type*: `boolean`

 Notify when workspace initialization is complete \(requires v1\.7\.0+\)\.

### `fortran-ls.useSignatureHelp`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Use signature help instead of snippets when available\.

### `fortran-ls.variableHover`

  * *Type*: `boolean`

 Show hover information for variables\.



