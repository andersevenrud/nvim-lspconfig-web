# Haskell (hie)

https://github.com/haskell/haskell-ide-engine

the following init_options are supported (see https://github.com/haskell/haskell-ide-engine#configuration):
```lua
init_options = {
  languageServerHaskell = {
    hlintOn = bool;
    maxNumberOfProblems = number;
    diagnosticsDebounceDuration = number;
    liquidOn = bool (default false);
    completionSnippetsOn = bool (default true);
    formatOnImportOn = bool (default true);
    formattingProvider = string (default "brittany", alternate "floskell");
  }
}
```
        

## Setup

```lua
require'lspconfig'.hie.setup{}
```


### Default values

```lua
cmd = { "hie-wrapper", "--lsp" }
filetypes = { "haskell" }
root_dir = root_pattern("stack.yaml", "package.yaml", ".git")
```


This server accepts configuration via the `settings` key.

## Available settings

### `haskell.completionSnippetsOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Show snippets with type information when using code completion

### `haskell.diagnosticsOnChange`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Compute diagnostics continuously as you type\. Turn off to only generate diagnostics on file save\.

### `haskell.formatOnImportOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 When adding an import\, use the formatter on the result

### `haskell.formattingProvider`

  `enum { "brittany", "floskell", "fourmolu", "ormolu", "stylish-haskell", "none" }`

 * *Default*: `"ormolu"`
 
 The formatter to use when formatting a document or range\. Ensure the plugin is enabled\.

### `haskell.hlintOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Get suggestions from hlint

### `haskell.logFile`

  * *Type*: `string`

 * *Default*: `""`
 
 If set\, redirects the logs to a file\.

### `haskell.plugin.class.globalOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enables type class plugin

### `haskell.plugin.eval.globalOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enables eval plugin

### `haskell.plugin.ghcide-completions.config.autoExtendOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `haskell.plugin.ghcide-completions.config.snippetsOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `haskell.plugin.ghcide-type-lenses.config.mode`

  `enum { "always", "exported", "diagnostics" }`

 * *Default*: `true`
 
 Control how type lenses are shown

### `haskell.plugin.ghcide-type-lenses.globalOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enables type lenses plugin

### `haskell.plugin.haddockComments.globalOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enables haddock comments plugin

### `haskell.plugin.hlint.codeActionsOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enables hlint code actions \(apply hints\)

### `haskell.plugin.hlint.diagnosticsOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enables hlint diagnostics

### `haskell.plugin.importLens.codeActionsOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enables explicit imports code actions

### `haskell.plugin.importLens.codeLensOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enables explicit imports code lenses

### `haskell.plugin.moduleName.globalOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enables module name plugin

### `haskell.plugin.pragmas.codeActionsOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enables pragmas code actions

### `haskell.plugin.pragmas.completionOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enables pragmas completions

### `haskell.plugin.retrie.globalOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enables retrie plugin

### `haskell.plugin.splice.globalOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enables splice plugin \(expand template haskell definitions\)

### `haskell.plugin.tactic.config.features`

  * *Type*: `string`

 * *Default*: `true`
 
 null

### `haskell.plugin.tactic.config.max_use_ctor_actions`

  * *Type*: `integer`

 * *Default*: `5`
 
 null

### `haskell.plugin.tactic.globalOn`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enables wingman \(tactic\) plugin

### `haskell.plugin.tactics.config.hole_severity`

  `enum { 1, 2, 3, 4, vim.NIL }`

 * *Default*: `vim.NIL`
 
 The severity to use when showing hole diagnostics\.

### `haskell.plugin.tactics.config.timeout_duration`

  * *Type*: `integer`

 * *Default*: `2`
 
 null

### `haskell.releasesURL`

  * *Type*: `string`

 * *Default*: `""`
 
 An optional URL to override where to check for haskell\-language\-server releases

### `haskell.serverExecutablePath`

  * *Type*: `string`

 * *Default*: `""`
 
 null

### `haskell.trace.server`

  `enum { "off", "messages" }`

 * *Default*: `"off"`
 
 Traces the communication between VS Code and the language server\.

### `haskell.updateBehavior`

  `enum { "keep-up-to-date", "prompt", "never-check" }`

 * *Default*: `"keep-up-to-date"`
 
 null



