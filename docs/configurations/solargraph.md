# Ruby (solargraph)

https://solargraph.org/

solargraph, a language server for Ruby

You can install solargraph via gem install.

```sh
gem install --user-install solargraph
```
    

## Setup

```lua
require'lspconfig'.solargraph.setup{}
```


### Default values

```lua
cmd = { "solargraph", "stdio" }
filetypes = { "ruby" }
root_dir = root_pattern("Gemfile", ".git")
settings = {
  solargraph = {
    diagnostics = true
  }
}
```


This server accepts configuration via the `settings` key.

## Available settings

### `solargraph.autoformat`

  `enum { true, false }`

 Enable automatic formatting while typing \(WARNING\: experimental\)

### `solargraph.bundlerPath`

  * *Type*: `string`

 * *Default*: `"bundle"`
 
 Path to the bundle executable\, defaults to \'bundle\'\. Needs to be an absolute path for the \'bundle\' exec\/shim

### `solargraph.checkGemVersion`

  `enum { true, false }`

 * *Default*: `true`
 
 Automatically check if a new version of the Solargraph gem is available\.

### `solargraph.commandPath`

  * *Type*: `string`

 * *Default*: `"solargraph"`
 
 Path to the solargraph command\.  Set this to an absolute path to select from multiple installed Ruby versions\.

### `solargraph.completion`

  `enum { true, false }`

 * *Default*: `true`
 
 Enable completion

### `solargraph.definitions`

  `enum { true, false }`

 * *Default*: `true`
 
 Enable definitions \(go to\, etc\.\)

### `solargraph.diagnostics`

  `enum { true, false }`

 Enable diagnostics

### `solargraph.externalServer`

  * *Type*: `object`

 * *Default*: `{host = "localhost",port = 7658}`
 
 The host and port to use for external transports\. \(Ignored for stdio and socket transports\.\)

### `solargraph.folding`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable folding ranges

### `solargraph.formatting`

  `enum { true, false }`

 Enable document formatting

### `solargraph.hover`

  `enum { true, false }`

 * *Default*: `true`
 
 Enable hover

### `solargraph.logLevel`

  `enum { "warn", "info", "debug" }`

 * *Default*: `"warn"`
 
 Level of debug info to log\. \`warn\` is least and \`debug\` is most\.

### `solargraph.references`

  `enum { true, false }`

 * *Default*: `true`
 
 Enable finding references

### `solargraph.rename`

  `enum { true, false }`

 * *Default*: `true`
 
 Enable symbol renaming

### `solargraph.symbols`

  `enum { true, false }`

 * *Default*: `true`
 
 Enable symbols

### `solargraph.transport`

  `enum { "socket", "stdio", "external" }`

 * *Default*: `"socket"`
 
 The type of transport to use\.

### `solargraph.useBundler`

  * *Type*: `boolean`

 Use \`bundle exec\` to run solargraph\. \(If this is true\, the solargraph\.commandPath setting is ignored\.\)



