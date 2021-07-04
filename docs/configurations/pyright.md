# Python (pyright)

https://github.com/microsoft/pyright

`pyright`, a static type checker and language server for python


## Setup

```lua
require'lspconfig'.pyright.setup{}
```

### Commands

- PyrightOrganizeImports: Organize Imports

### Default values

```lua
cmd = { "pyright-langserver", "--stdio" }
filetypes = { "python" }
root_dir = function(filename)
      return util.root_pattern(unpack(root_files))(filename) or util.path.dirname(filename)
    end,
settings = {
  python = {
    analysis = {
      autoSearchPaths = true,
      diagnosticMode = "workspace",
      useLibraryCodeForTypes = true
    }
  }
}
```


This server accepts configuration via the `settings` key.

## Available settings

### `pyright.disableLanguageServices`

  * *Type*: `boolean`

 Disables type completion\, definitions\, and references\.

### `pyright.disableOrganizeImports`

  * *Type*: `boolean`

 Disables the “Organize Imports” command\.

### `python.analysis.autoImportCompletions`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Offer auto\-import completions\.

### `python.analysis.autoSearchPaths`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Automatically add common search paths like \'src\'\?

### `python.analysis.diagnosticMode`

  `enum { "openFilesOnly", "workspace" }`

 * *Default*: `"openFilesOnly"`
 
 null

### `python.analysis.diagnosticSeverityOverrides`

  * *Type*: `object`

 * *Default*: `vim.empty_dict()`
 
 Allows a user to override the severity levels for individual diagnostics\.

### `python.analysis.extraPaths`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 Additional import search resolution paths

### `python.analysis.logLevel`

  `enum { "Error", "Warning", "Information", "Trace" }`

 * *Default*: `"Information"`
 
 Specifies the level of logging for the Output panel

### `python.analysis.stubPath`

  * *Type*: `string`

 * *Default*: `"typings"`
 
 Path to directory containing custom type stub files\.

### `python.analysis.typeCheckingMode`

  `enum { "off", "basic", "strict" }`

 * *Default*: `"basic"`
 
 Defines the default rule set for type checking\.

### `python.analysis.typeshedPaths`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 Paths to look for typeshed modules\.

### `python.analysis.useLibraryCodeForTypes`

  * *Type*: `boolean`

 Use library implementations to extract type information when type stub is not present\.

### `python.pythonPath`

  * *Type*: `string`

 * *Default*: `"python"`
 
 Path to Python\, you can use a custom version of Python\.

### `python.venvPath`

  * *Type*: `string`

 * *Default*: `""`
 
 Path to folder with a list of Virtual Environments\.



