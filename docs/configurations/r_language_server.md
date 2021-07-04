# R (r_language_server)

    [languageserver](https://github.com/REditorSupport/languageserver) is an
    implementation of the Microsoft's Language Server Protocol for the R
    language.

    It is released on CRAN and can be easily installed by

    ```R
    install.packages("languageserver")
    ```
    

## Setup

```lua
require'lspconfig'.r_language_server.setup{}
```


### Default values

```lua
cmd = { "R", "--slave", "-e", "languageserver::run()" }
filetypes = { "r", "rmd" }
log_level = 2
root_dir = root_pattern(".git") or os_homedir
```


This server accepts configuration via the `settings` key.

## Available settings

### `r.lsp.args`

  * *Type*: `array`

 * *Default*: `{}`
 
 The command line arguments to use when launching R Language Server

### `r.lsp.debug`

  * *Type*: `boolean`

 Debug R Language Server

### `r.lsp.diagnostics`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable Diagnostics

### `r.lsp.lang`

  * *Type*: `string`

 * *Default*: `""`
 
 Override default LANG environment variable

### `r.lsp.path`

  * *Type*: `string`

 * *Default*: `""`
 
 Path to R binary for launching Language Server

### `r.lsp.use_stdio`

  * *Type*: `boolean`

 Use STDIO connection instead of TCP\. \(Unix\/macOS users only\)

### `r.rpath.linux`

  * *Type*: `string`

 * *Default*: `""`
 
 Path to an R executable for Linux\. Must be \"vanilla\" R\, not radian etc\.\!

### `r.rpath.mac`

  * *Type*: `string`

 * *Default*: `""`
 
 Path to an R executable for macOS\. Must be \"vanilla\" R\, not radian etc\.\!

### `r.rpath.windows`

  * *Type*: `string`

 * *Default*: `""`
 
 Path to an R executable for Windows\. Must be \"vanilla\" R\, not radian etc\.\!



