# Nim (nimls)

https://github.com/PMunch/nimlsp
`nimlsp` can be installed via the `nimble` package manager:
```sh
nimble install nimlsp
```
    

## Setup

```lua
require'lspconfig'.nimls.setup{}
```


### Default values

```lua
cmd = { "nimlsp" }
filetypes = { "nim" }
root_dir = root_pattern(".git") or os_homedir
```


This server accepts configuration via the `settings` key.

## Available settings

### `nim.buildCommand`

  * *Type*: `string`

 * *Default*: `"c"`
 
 Nim build command \(c\, cpp\, doc\, etc\)

### `nim.buildOnSave`

  * *Type*: `boolean`

 Execute build task from tasks\.json file on save\.

### `nim.enableNimsuggest`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable calling nimsuggest process to provide completion suggestions\, hover suggestions\, etc\.
 This option requires restart to take effect\.

### `nim.licenseString`

  * *Type*: `string`

 * *Default*: `""`
 
 Optional license text that will be inserted on nim file creation\.

### `nim.lintOnSave`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Check code by using \'nim check\' on save\.

### `nim.logNimsuggest`

  * *Type*: `boolean`

 Enable verbose logging of nimsuggest to use profile directory\.

### `nim.nimprettyIndent`

  * *Type*: `integer`

 * *Default*: `0`
 
 Nimpretty\: set the number of spaces that is used for indentation
 \-\-indent\:0 means autodetection \(default behaviour\)\.

### `nim.nimprettyMaxLineLen`

  * *Type*: `integer`

 * *Default*: `80`
 
 Nimpretty\: set the desired maximum line length \(default\: 80\)\.

### `nim.nimsuggestRestartTimeout`

  * *Type*: `integer`

 * *Default*: `60`
 
 Nimsuggest will be restarted after this timeout in minutes\, if 0 then restart disabled\.
 This option requires restart to take effect\.

### `nim.project`

  * *Type*: `array`

 * *Default*: `{}`
 
 Nim project file\, if empty use current selected\.

### `nim.projectMapping`

  * *Type*: `object`

 * *Default*: `vim.empty_dict()`
 
 For non project mode list of per file project mapping using regex\, for example \`\`\`\{\"\(\.\*\)\.inim\"\: \"\$1\.nim\"\}\`\`\`

### `nim.runOutputDirectory`

  * *Type*: `string`

 * *Default*: `""`
 
 Output directory for run selected file command\. The directory is relative to the workspace root\.

### `nim.test-project`

  * *Type*: `string`

 * *Default*: `""`
 
 Optional test project\.



