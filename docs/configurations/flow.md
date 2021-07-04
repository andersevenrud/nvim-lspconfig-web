# TypeScript (flow)

https://flow.org/
https://github.com/facebook/flow

See below for how to setup Flow itself.
https://flow.org/en/docs/install/

See below for lsp command options.

```sh
npx flow lsp --help
```
    

## Setup

```lua
require'lspconfig'.flow.setup{}
```


### Default values

```lua
cmd = { "npx", "--no-install", "flow", "lsp" }
filetypes = { "javascript", "javascriptreact", "javascript.jsx" }
root_dir = root_pattern(".flowconfig")
```


This server accepts configuration via the `settings` key.

## Available settings

### `flow.coverageSeverity`

  `enum { "error", "warn", "info" }`

 * *Default*: `"info"`
 
 Type coverage diagnostic severity

### `flow.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Is flow enabled

### `flow.fileExtensions`

  * *Type*: `array`

 * *Default*: `{ ".js", ".mjs", ".jsx", ".flow", ".json" }`
 
 * *Array items*: `{type = "string"}`
 
 \(Supported only when useLSP\: false\)\. File extensions to consider for flow processing

### `flow.lazyMode`

  * *Type*: `string`

 * *Default*: `vim.NIL`
 
 Set value to enable flow lazy mode

### `flow.logLevel`

  `enum { "error", "warn", "info", "trace" }`

 * *Default*: `"info"`
 
 Log level for output panel logs

### `flow.pathToFlow`

  * *Type*: `string`

 * *Default*: `"flow"`
 
 Absolute path to flow binary\. Special var \$\{workspaceFolder\} or \$\{flowconfigDir\} can be used in path \(NOTE\: in windows you can use \'\/\' and can omit \'\.cmd\' in path\)

### `flow.runOnAllFiles`

  * *Type*: `boolean`

 \(Supported only when useLSP\: false\) Run Flow on all files\, No need to put \/\/\@flow comment on top of files\.

### `flow.runOnEdit`

  * *Type*: `boolean`

 * *Default*: `true`
 
 If true will run flow on every edit\, otherwise will run only when changes are saved \(Note\: \'useLSP\: true\' only supports syntax errors\)

### `flow.showStatus`

  * *Type*: `boolean`

 * *Default*: `true`
 
 \(Supported only when useLSP\: false\) If true will display flow status is the statusbar

### `flow.showUncovered`

  * *Type*: `boolean`

 If true will show uncovered code by default

### `flow.stopFlowOnExit`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Stop Flow on Exit

### `flow.trace.server`

  

 * *Default*: `"off"`
 
 Traces the communication between VSCode and the flow lsp service\.

### `flow.useBundledFlow`

  * *Type*: `boolean`

 * *Default*: `true`
 
 If true will use flow bundled with this plugin if nothing works

### `flow.useCodeSnippetOnFunctionSuggest`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Complete functions with their parameter signature\.

### `flow.useLSP`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Turn off to switch from the official Flow Language Server implementation to talking directly to flow\.

### `flow.useNPMPackagedFlow`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Support using flow through your node\_modules folder\, WARNING\: Checking this box is a security risk\. When you open a project we will immediately run code contained within it\.



