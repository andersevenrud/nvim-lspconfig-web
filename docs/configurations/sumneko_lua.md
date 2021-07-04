# Lua (sumneko_lua)

https://github.com/sumneko/lua-language-server

Lua language server.

`lua-language-server` can be installed by following the instructions [here](https://github.com/sumneko/lua-language-server/wiki/Build-and-Run-(Standalone)).

**By default, lua-language-server doesn't have a `cmd` set.** This is because nvim-lspconfig does not make assumptions about your path. You must add the following to your init.vim or init.lua to set `cmd` to the absolute path ($HOME and ~ are not expanded) of your unzipped and compiled lua-language-server.

```lua
local system_name
if vim.fn.has("mac") == 1 then
  system_name = "macOS"
elseif vim.fn.has("unix") == 1 then
  system_name = "Linux"
elseif vim.fn.has('win32') == 1 then
  system_name = "Windows"
else
  print("Unsupported system for sumneko")
end

-- set the path to the sumneko installation; if you previously installed via the now deprecated :LspInstall, use
local sumneko_root_path = vim.fn.stdpath('cache')..'/lspconfig/sumneko_lua/lua-language-server'
local sumneko_binary = sumneko_root_path.."/bin/"..system_name.."/lua-language-server"

local runtime_path = vim.split(package.path, ';')
table.insert(runtime_path, "lua/?.lua")
table.insert(runtime_path, "lua/?/init.lua")

require'lspconfig'.sumneko_lua.setup {
  cmd = {sumneko_binary, "-E", sumneko_root_path .. "/main.lua"};
  settings = {
    Lua = {
      runtime = {
        -- Tell the language server which version of Lua you're using (most likely LuaJIT in the case of Neovim)
        version = 'LuaJIT',
        -- Setup your lua path
        path = runtime_path,
      },
      diagnostics = {
        -- Get the language server to recognize the `vim` global
        globals = {'vim'},
      },
      workspace = {
        -- Make the server aware of Neovim runtime files
        library = vim.api.nvim_get_runtime_file("", true),
      },
      -- Do not send telemetry data containing a randomized but unique identifier
      telemetry = {
        enable = false,
      },
    },
  },
}
```


## Setup

```lua
require'lspconfig'.sumneko_lua.setup{}
```


### Default values

```lua
filetypes = { "lua" }
log_level = 2
root_dir = root_pattern(".git") or bufdir
settings = {
  Lua = {
    telemetry = {
      enable = false
    }
  }
}
```


This server accepts configuration via the `settings` key.

## Available settings

### `Lua.color.mode`

  `enum { "Grammar", "Semantic" }`

 * *Default*: `"Semantic"`
 
 null

### `Lua.completion.autoRequire`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `Lua.completion.callSnippet`

  `enum { "Disable", "Both", "Replace" }`

 * *Default*: `"Disable"`
 
 null

### `Lua.completion.displayContext`

  * *Type*: `integer`

 * *Default*: `6`
 
 null

### `Lua.completion.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `Lua.completion.keywordSnippet`

  `enum { "Disable", "Both", "Replace" }`

 * *Default*: `"Replace"`
 
 null

### `Lua.completion.showParams`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `Lua.completion.workspaceWord`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `Lua.diagnostics.disable`

  * *Type*: `array`

 * *Array items*: `{type = "string"}`
 
 null

### `Lua.diagnostics.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `Lua.diagnostics.globals`

  * *Type*: `array`

 * *Array items*: `{type = "string"}`
 
 null

### `Lua.diagnostics.neededFileStatus`

  * *Type*: `object`

 null

### `Lua.diagnostics.severity`

  * *Type*: `object`

 null

### `Lua.diagnostics.workspaceDelay`

  * *Type*: `integer`

 * *Default*: `0`
 
 null

### `Lua.diagnostics.workspaceRate`

  * *Type*: `integer`

 * *Default*: `100`
 
 null

### `Lua.hint.enable`

  * *Type*: `boolean`

 null

### `Lua.hint.paramName`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `Lua.hint.paramType`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `Lua.hint.setType`

  * *Type*: `boolean`

 null

### `Lua.hover.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `Lua.hover.enumsLimit`

  * *Type*: `integer`

 * *Default*: `5`
 
 null

### `Lua.hover.previewFields`

  * *Type*: `integer`

 * *Default*: `20`
 
 null

### `Lua.hover.viewNumber`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `Lua.hover.viewString`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `Lua.hover.viewStringMax`

  * *Type*: `integer`

 * *Default*: `1000`
 
 null

### `Lua.misc.parameters`

  * *Type*: `array`

 * *Array items*: `{type = "string"}`
 
 null

### `Lua.runtime.builtin`

  * *Type*: `object`

 null

### `Lua.runtime.fileEncoding`

  `enum { "utf8", "ansi" }`

 * *Default*: `"utf8"`
 
 null

### `Lua.runtime.nonstandardSymbol`

  * *Type*: `array`

 * *Array items*: `{enum = { "//", "/**/", "`", "+=", "-=", "*=", "/=", "||", "&&", "!", "!=", "continue" },type = "string"}`
 
 null

### `Lua.runtime.path`

  * *Type*: `array`

 * *Default*: `{ "?.lua", "?/init.lua", "?/?.lua" }`
 
 * *Array items*: `{type = "string"}`
 
 null

### `Lua.runtime.plugin`

  * *Type*: `string`

 * *Default*: `""`
 
 null

### `Lua.runtime.special`

  * *Type*: `object`

 null

### `Lua.runtime.unicodeName`

  * *Type*: `boolean`

 null

### `Lua.runtime.version`

  `enum { "Lua 5.1", "Lua 5.2", "Lua 5.3", "Lua 5.4", "LuaJIT" }`

 * *Default*: `"Lua 5.4"`
 
 null

### `Lua.signatureHelp.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `Lua.telemetry.enable`

  * *Type*: `boolean|null`

 * *Default*: `vim.NIL`
 
 null

### `Lua.window.progressBar`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `Lua.window.statusBar`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `Lua.workspace.ignoreDir`

  * *Type*: `array`

 * *Default*: `{ ".vscode" }`
 
 * *Array items*: `{type = "string"}`
 
 null

### `Lua.workspace.ignoreSubmodules`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `Lua.workspace.library`

  * *Type*: `array`

 * *Array items*: `{type = "string"}`
 
 null

### `Lua.workspace.maxPreload`

  * *Type*: `integer`

 * *Default*: `1000`
 
 null

### `Lua.workspace.preloadFileSize`

  * *Type*: `integer`

 * *Default*: `100`
 
 null

### `Lua.workspace.useGitIgnore`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null



