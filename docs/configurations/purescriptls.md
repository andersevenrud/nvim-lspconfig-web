# PureScript (purescriptls)

https://github.com/nwolverson/purescript-language-server
`purescript-language-server` can be installed via `npm`
```sh
npm install -g purescript-language-server
```


## Setup

```lua
require'lspconfig'.purescriptls.setup{}
```


### Default values

```lua
cmd = { "purescript-language-server", "--stdio" }
filetypes = { "purescript" }
root_dir = root_pattern("spago.dhall, bower.json")
```


This server accepts configuration via the `settings` key.

## Available settings

### `purescript.addNpmPath`

  * *Type*: `boolean`

 Whether to add the local npm bin directory to the PATH for purs IDE server and build command\.

### `purescript.addPscPackageSources`

  * *Type*: `boolean`

 Whether to add psc\-package sources to the globs passed to the IDE server for source locations \(specifically the output of \`psc\-package sources\`\, if this is a psc\-package project\)\. Update due to adding packages\/changing package set requires psc\-ide server restart\.

### `purescript.addSpagoSources`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to add spago sources to the globs passed to the IDE server for source locations \(specifically the output of \`spago sources\`\, if this is a spago project\)\. Update due to adding packages\/changing package set requires psc\-ide server restart\.

### `purescript.autoStartPscIde`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to automatically start\/connect to purs IDE server when editing a PureScript file \(includes connecting to an existing running instance\)\. If this is disabled\, various features like autocomplete\, tooltips\, and other type info will not work until start command is run manually\.

### `purescript.autocompleteAddImport`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to automatically add imported identifiers when accepting autocomplete result\.

### `purescript.autocompleteAllModules`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to always autocomplete from all built modules\, or just those imported in the file\. Suggestions from all modules always available by explicitly triggering autocomplete\.

### `purescript.autocompleteGrouped`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to group completions in autocomplete results\. Requires compiler 0\.11\.6

### `purescript.autocompleteLimit`

  * *Type*: `null|integer`

 * *Default*: `vim.NIL`
 
 Maximum number of results to fetch for an autocompletion request\. May improve performance on large projects\.

### `purescript.buildCommand`

  * *Type*: `string`

 * *Default*: `"spago build --purs-args --json-errors"`
 
 Build command to use with arguments\. Not passed to shell\. eg \`spago build \-\-purs\-args \-\-json\-errors\`

### `purescript.censorWarnings`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 The warning codes to censor\, both for fast rebuild and a full build\. Unrelated to any psa setup\. e\.g\.\: \[\"ShadowedName\"\,\"MissingTypeDeclaration\"\]

### `purescript.codegenTargets`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 * *Array items*: `{type = "string"}`
 
 List of codegen targets to pass to the compiler for rebuild\. e\.g\. js\, corefn\. If not specified \(rather than empty array\) this will not be passed and the compiler will default to js\. Requires 0\.12\.1+

### `purescript.fastRebuild`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable purs IDE server fast rebuild

### `purescript.importsPreferredModules`

  * *Type*: `array`

 * *Default*: `{ "Prelude" }`
 
 * *Array items*: `{type = "string"}`
 
 Module to prefer to insert when adding imports which have been re\-exported\. In order of preference\, most preferred first\.

### `purescript.outputDirectory`

  * *Type*: `string`

 * *Default*: `"output/"`
 
 Override purs ide output directory \(output\/ if not specified\)\. This should match up to your build command

### `purescript.packagePath`

  * *Type*: `string`

 * *Default*: `""`
 
 Path to installed packages\. Will be used to control globs passed to IDE server for source locations\.  Change requires IDE server restart\.

### `purescript.preludeModule`

  * *Type*: `string`

 * *Default*: `"Prelude"`
 
 Module to consider as your default prelude\, if an auto\-complete suggestion comes from this module it will be imported unqualified\.

### `purescript.pscIdePort`

  * *Type*: `integer|null`

 * *Default*: `vim.NIL`
 
 Port to use for purs IDE server \(whether an existing server or to start a new one\)\. By default a random port is chosen \(or an existing port in \.psc\-ide\-port if present\)\, if this is specified no attempt will be made to select an alternative port on failure\.

### `purescript.pscIdelogLevel`

  * *Type*: `string`

 * *Default*: `""`
 
 Log level for purs IDE server

### `purescript.pursExe`

  * *Type*: `string`

 * *Default*: `"purs"`
 
 Location of purs executable \(resolved wrt PATH\)

### `purescript.sourcePath`

  * *Type*: `string`

 * *Default*: `"src"`
 
 Path to application source root\. Will be used to control globs passed to IDE server for source locations\. Change requires IDE server restart\.

### `purescript.trace.server`

  `enum { "off", "messages", "verbose" }`

 * *Default*: `"off"`
 
 Traces the communication between VSCode and the PureScript language service\.



