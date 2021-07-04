# Python (pyls)

https://github.com/palantir/python-language-server

`python-language-server`, a language server for Python.

The language server can be installed via `pipx install 'python-language-server[all]'`.

    

## Setup

```lua
require'lspconfig'.pyls.setup{}
```


### Default values

```lua
cmd = { "pyls" }
filetypes = { "python" }
root_dir = vim's starting directory
```


This server accepts configuration via the `settings` key.

## Available settings

### `pyls.configurationSources`

  * *Type*: `array`

 * *Default*: `{ "pycodestyle" }`
 
 * *Array items*: `{enum = { "pycodestyle", "pyflakes" },type = "string"}`
 
 List of configuration sources to use\.

### `pyls.executable`

  * *Type*: `string`

 * *Default*: `"pyls"`
 
 Language server executable

### `pyls.plugins.jedi.env_vars`

  * *Type*: `dictionary`

 * *Default*: `vim.NIL`
 
 Define environment variables for jedi\.Script and Jedi\.names\.

### `pyls.plugins.jedi.environment`

  * *Type*: `string`

 * *Default*: `vim.NIL`
 
 Define environment for jedi\.Script and Jedi\.names\.

### `pyls.plugins.jedi.extra_paths`

  * *Type*: `array`

 * *Default*: `{}`
 
 Define extra paths for jedi\.Script\.

### `pyls.plugins.jedi_completion.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable or disable the plugin\.

### `pyls.plugins.jedi_completion.fuzzy`

  * *Type*: `boolean`

 Enable fuzzy when requesting autocomplete\.

### `pyls.plugins.jedi_completion.include_class_objects`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Adds class objects as a separate completion item\.

### `pyls.plugins.jedi_completion.include_params`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Auto\-completes methods and classes with tabstops for each parameter\.

### `pyls.plugins.jedi_definition.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable or disable the plugin\.

### `pyls.plugins.jedi_definition.follow_builtin_imports`

  * *Type*: `boolean`

 * *Default*: `true`
 
 If follow\_imports is True will decide if it follow builtin imports\.

### `pyls.plugins.jedi_definition.follow_imports`

  * *Type*: `boolean`

 * *Default*: `true`
 
 The goto call will follow imports\.

### `pyls.plugins.jedi_hover.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable or disable the plugin\.

### `pyls.plugins.jedi_references.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable or disable the plugin\.

### `pyls.plugins.jedi_signature_help.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable or disable the plugin\.

### `pyls.plugins.jedi_symbols.all_scopes`

  * *Type*: `boolean`

 * *Default*: `true`
 
 If True lists the names of all scopes instead of only the module namespace\.

### `pyls.plugins.jedi_symbols.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable or disable the plugin\.

### `pyls.plugins.mccabe.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable or disable the plugin\.

### `pyls.plugins.mccabe.threshold`

  * *Type*: `number`

 * *Default*: `15`
 
 The minimum threshold that triggers warnings about cyclomatic complexity\.

### `pyls.plugins.preload.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable or disable the plugin\.

### `pyls.plugins.preload.modules`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 * *Array items*: `{type = "string"}`
 
 List of modules to import on startup

### `pyls.plugins.pycodestyle.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable or disable the plugin\.

### `pyls.plugins.pycodestyle.exclude`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 * *Array items*: `{type = "string"}`
 
 Exclude files or directories which match these patterns\.

### `pyls.plugins.pycodestyle.filename`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 * *Array items*: `{type = "string"}`
 
 When parsing directories\, only check filenames matching these patterns\.

### `pyls.plugins.pycodestyle.hangClosing`

  * *Type*: `boolean`

 * *Default*: `vim.NIL`
 
 Hang closing bracket instead of matching indentation of opening bracket\'s line\.

### `pyls.plugins.pycodestyle.ignore`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 * *Array items*: `{type = "string"}`
 
 Ignore errors and warnings

### `pyls.plugins.pycodestyle.maxLineLength`

  * *Type*: `number`

 * *Default*: `vim.NIL`
 
 Set maximum allowed line length\.

### `pyls.plugins.pycodestyle.select`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 * *Array items*: `{type = "string"}`
 
 Select errors and warnings

### `pyls.plugins.pydocstyle.addIgnore`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 * *Array items*: `{type = "string"}`
 
 Ignore errors and warnings in addition to the specified convention\.

### `pyls.plugins.pydocstyle.addSelect`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 * *Array items*: `{type = "string"}`
 
 Select errors and warnings in addition to the specified convention\.

### `pyls.plugins.pydocstyle.convention`

  `enum { "pep257", "numpy" }`

 * *Default*: `vim.NIL`
 
 Choose the basic list of checked errors by specifying an existing convention\.

### `pyls.plugins.pydocstyle.enabled`

  * *Type*: `boolean`

 Enable or disable the plugin\.

### `pyls.plugins.pydocstyle.ignore`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 * *Array items*: `{type = "string"}`
 
 Ignore errors and warnings

### `pyls.plugins.pydocstyle.match`

  * *Type*: `string`

 * *Default*: `"(?!test_).*\\.py"`
 
 Check only files that exactly match the given regular expression\; default is to match files that don\'t start with \'test\_\' but end with \'\.py\'\.

### `pyls.plugins.pydocstyle.matchDir`

  * *Type*: `string`

 * *Default*: `"[^\\.].*"`
 
 Search only dirs that exactly match the given regular expression\; default is to match dirs which do not begin with a dot\.

### `pyls.plugins.pydocstyle.select`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 * *Array items*: `{type = "string"}`
 
 Select errors and warnings

### `pyls.plugins.pyflakes.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable or disable the plugin\.

### `pyls.plugins.pylint.args`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 * *Array items*: `{type = "string"}`
 
 Arguments to pass to pylint\.

### `pyls.plugins.pylint.enabled`

  * *Type*: `boolean`

 Enable or disable the plugin\.

### `pyls.plugins.pylint.executable`

  * *Type*: `string`

 * *Default*: `vim.NIL`
 
 Executable to run pylint with\. Enabling this will run pylint on unsaved files via stdin\. Can slow down workflow\. Only works with python3\.

### `pyls.plugins.rope_completion.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable or disable the plugin\.

### `pyls.plugins.yapf.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable or disable the plugin\.

### `pyls.rope.extensionModules`

  * *Type*: `string`

 * *Default*: `vim.NIL`
 
 Builtin and c\-extension modules that are allowed to be imported and inspected by rope\.

### `pyls.rope.ropeFolder`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 * *Array items*: `{type = "string"}`
 
 The name of the folder in which rope stores project configurations and data\.  Pass \`null\` for not using such a folder at all\.



