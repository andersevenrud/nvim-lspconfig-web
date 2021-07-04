# YAML (yamlls)

https://github.com/redhat-developer/yaml-language-server

`yaml-language-server` can be installed via `npm`:
```sh
npm install -g yaml-language-server
```


## Setup

```lua
require'lspconfig'.yamlls.setup{}
```


### Default values

```lua
cmd = { "yaml-language-server", "--stdio" }
filetypes = { "yaml" }
root_dir = root_pattern(".git", vim.fn.getcwd())
```


This server accepts configuration via the `settings` key.

## Available settings

### `redhat.telemetry.enabled`

  * *Type*: `boolean`

 * *Default*: `vim.NIL`
 
 null

### `yaml.completion`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable\/disable completion feature

### `yaml.customTags`

  * *Type*: `array`

 * *Default*: `{}`
 
 Custom tags for the parser to use

### `yaml.disableAdditionalProperties`

  * *Type*: `boolean`

 Globally set additionalProperties to false for all objects\. So if its true\, no extra properties are allowed inside yaml\.

### `yaml.format.bracketSpacing`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Print spaces between brackets in objects

### `yaml.format.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable\/disable default YAML formatter

### `yaml.format.printWidth`

  * *Type*: `integer`

 * *Default*: `80`
 
 Specify the line length that the printer will wrap on

### `yaml.format.proseWrap`

  `enum { "preserve", "never", "always" }`

 * *Default*: `"preserve"`
 
 Always\: wrap prose if it exeeds the print width\, Never\: never wrap the prose\, Preserve\: wrap prose as\-is

### `yaml.format.singleQuote`

  * *Type*: `boolean`

 Use single quotes instead of double quotes

### `yaml.hover`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable\/disable hover feature

### `yaml.maxItemsComputed`

  * *Type*: `integer`

 * *Default*: `5000`
 
 The maximum number of outline symbols and folding regions computed \(limited for performance reasons\)\.

### `yaml.schemaStore.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Automatically pull available YAML schemas from JSON Schema Store

### `yaml.schemaStore.url`

  * *Type*: `string`

 * *Default*: `"https://www.schemastore.org/api/json/catalog.json"`
 
 URL of schema store catalog to use

### `yaml.schemas`

  * *Type*: `object`

 * *Default*: `vim.empty_dict()`
 
 Associate schemas to YAML files in the current workspace

### `yaml.trace.server`

  `enum { "off", "messages", "verbose" }`

 * *Default*: `"off"`
 
 Traces the communication between VSCode and the YAML language service\.

### `yaml.validate`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable\/disable validation feature



