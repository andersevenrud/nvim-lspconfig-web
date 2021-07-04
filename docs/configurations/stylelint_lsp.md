# Stylelint (stylelint_lsp)

https://github.com/bmatcuk/stylelint-lsp

`stylelint-lsp` can be installed via `npm`:

```sh
npm i -g stylelint-lsp
```

Can be configured by passing a `settings.stylelintplus` object to `stylelint_lsp.setup`:

```lua
require'lspconfig'.stylelint_lsp.setup{
  settings = {
    stylelintplus = {
      -- see available options in stylelint-lsp documentation
    }
  }
}
```


## Setup

```lua
require'lspconfig'.stylelint_lsp.setup{}
```


### Default values

```lua
cmd = { "stylelint-lsp", "--stdio" }
filetypes = { "css", "less", "scss", "sugarss", "vue", "wxss", "javascript", "javascriptreact", "typescript", "typescriptreact" }
root_dir =  root_pattern('.stylelintrc', 'package.json') 
settings = {}
```


This server accepts configuration via the `settings` key.

## Available settings

### `stylelintplus.autoFixOnFormat`

  * *Type*: `boolean`

 Auto\-fix on format request\.

### `stylelintplus.autoFixOnSave`

  * *Type*: `boolean`

 Auto\-fix and format on save\.

### `stylelintplus.config`

  * *Type*: `object`

 * *Default*: `vim.NIL`
 
 Stylelint config\. If config and configFile are unset\, stylelint will automatically look for a config file\.

### `stylelintplus.configFile`

  * *Type*: `string`

 * *Default*: `vim.NIL`
 
 Stylelint config file\. If config and configFile are unset\, stylelint will automatically look for a config file\.

### `stylelintplus.configOverrides`

  * *Type*: `object`

 * *Default*: `vim.NIL`
 
 Stylelint config overrides\. These will be applied on top of the config\, configFile\, or auto\-discovered config file loaded by stylelint\.

### `stylelintplus.cssInJs`

  * *Type*: `boolean`

 Run stylelint on javascript\/typescript files\.

### `stylelintplus.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 If false\, stylelint will not validate the file\.

### `stylelintplus.filetypes`

  * *Type*: `array`

 * *Default*: `{ "css", "less", "postcss", "scss", "sugarss", "vue", "wxss" }`
 
 * *Array items*: `{type = "string"}`
 
 Filetypes that coc\-stylelintplus will lint\.

### `stylelintplus.trace.server`

  `enum { "off", "messages", "verbose" }`

 * *Default*: `"off"`
 
 Capture trace messages from the server\.

### `stylelintplus.validateOnSave`

  * *Type*: `boolean`

 Validate after saving\. Automatically enabled if autoFixOnSave is enabled\.

### `stylelintplus.validateOnType`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Validate after making changes\.



