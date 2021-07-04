# Elm (elmls)

https://github.com/elm-tooling/elm-language-server#installation

If you don't want to use Nvim to install it, then you can use:
```sh
npm install -g elm elm-test elm-format @elm-tooling/elm-language-server
```


## Setup

```lua
require'lspconfig'.elmls.setup{}
```


### Default values

```lua
cmd = { "elm-language-server" }
filetypes = { "elm" }
init_options = {
  elmAnalyseTrigger = "change",
  elmFormatPath = "elm-format",
  elmPath = "elm",
  elmTestPath = "elm-test"
}
root_dir = root_pattern("elm.json")
```


This server accepts configuration via the `settings` key.

## Available settings

### `elmLS.disableElmLSDiagnostics`

  * *Type*: `boolean`

 Disable linting diagnostics from the language server\.

### `elmLS.elmFormatPath`

  * *Type*: `string`

 * *Default*: `""`
 
 The path to your elm\-format executable\. Should be empty by default\, in that case it will assume the name and try to first get it from a local npm installation or a global one\. If you set it manually it will not try to load from the npm folder\.

### `elmLS.elmPath`

  * *Type*: `string`

 * *Default*: `""`
 
 The path to your elm executable\. Should be empty by default\, in that case it will assume the name and try to first get it from a local npm installation or a global one\. If you set it manually it will not try to load from the npm folder\.

### `elmLS.elmReviewDiagnostics`

  `enum { "off", "warning", "error" }`

 * *Default*: `"off"`
 
 Set severity or disable linting diagnostics for elm\-review\.

### `elmLS.elmReviewPath`

  * *Type*: `string`

 * *Default*: `""`
 
 The path to your elm\-review executable\. Should be empty by default\, in that case it will assume the name and try to first get it from a local npm installation or a global one\. If you set it manually it will not try to load from the npm folder\.

### `elmLS.elmTestPath`

  * *Type*: `string`

 * *Default*: `""`
 
 The path to your elm\-test executable\. Should be empty by default\, in that case it will assume the name and try to first get it from a local npm installation or a global one\. If you set it manually it will not try to load from the npm folder\.

### `elmLS.elmTestRunner.showElmTestOutput`

  * *Type*: `boolean`

 Show output of elm\-test as terminal task

### `elmLS.onlyUpdateDiagnosticsOnSave`

  * *Type*: `boolean`

 Only update compiler diagnostics on save\, not on document change\.

### `elmLS.skipInstallPackageConfirmation`

  * *Type*: `boolean`

 Skips confirmation for the Install Package code action\.

### `elmLS.trace.server`

  `enum { "off", "messages", "verbose" }`

 * *Default*: `"off"`
 
 Traces the communication between VS Code and the language server\.



