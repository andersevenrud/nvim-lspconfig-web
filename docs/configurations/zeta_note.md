# Markdown (zeta_note)

https://github.com/artempyanykh/zeta-note

Markdown LSP server for easy note-taking with cross-references and diagnostics.

Binaries can be downloaded from https://github.com/artempyanykh/zeta-note/releases

**By default, zeta-note doesn't have a `cmd` set.** This is because nvim-lspconfig does not make assumptions about your path. You must add the following to your init.vim or init.lua to set `cmd` to the absolute path ($HOME and ~ are not expanded) of your zeta-note binary.

```lua
require'lspconfig'.zeta_note.setup{
  cmd = {'path/to/zeta-note'}
}
```


## Setup

```lua
require'lspconfig'.zeta_note.setup{}
```


### Default values

```lua
filetypes = { "markdown" }
root_dir = root_pattern(".zeta.toml")
```


This server accepts configuration via the `settings` key.

## Available settings

### `zetaNote.customCommand`

  * *Type*: `string`

 When set use this command to run the language server\.
 The command is split on spaces\: first part is the command name\, the rest is the arguments\.

### `zetaNote.customCommandDir`

  * *Type*: `string`

 null

### `zetaNote.trace.server`

  `enum { "off", "messages", "verbose" }`

 * *Default*: `"verbose"`
 
 Level of verbosity in communicating with the server



