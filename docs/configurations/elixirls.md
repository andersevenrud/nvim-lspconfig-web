# Elexir (elixirls)

https://github.com/elixir-lsp/elixir-ls

`elixir-ls` can be installed by following the instructions [here](https://github.com/elixir-lsp/elixir-ls#building-and-running).

```bash
curl -fLO https://github.com/elixir-lsp/elixir-ls/releases/latest/download/elixir-ls.zip
unzip elixir-ls.zip -d /path/to/elixir-ls
# Unix
chmod +x /path/to/elixir-ls/language_server.sh
```

**By default, elixir-ls doesn't have a `cmd` set.** This is because nvim-lspconfig does not make assumptions about your path. You must add the following to your init.vim or init.lua to set `cmd` to the absolute path ($HOME and ~ are not expanded) of your unzipped elixir-ls.

```lua
require'lspconfig'.elixirls.setup{
    -- Unix
    cmd = { "/path/to/elixir-ls/language_server.sh" };
    -- Windows
    cmd = { "/path/to/elixir-ls/language_server.bat" };
    ...
}
```


## Setup

```lua
require'lspconfig'.elixirls.setup{}
```


### Default values

```lua
filetypes = { "elixir", "eelixir" }
root_dir = root_pattern("mix.exs", ".git") or vim.loop.os_homedir()
```


This server accepts configuration via the `settings` key.

## Available settings

### `elixirLS.dialyzerEnabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Run ElixirLS\'s rapid Dialyzer when code is saved

### `elixirLS.dialyzerFormat`

  `enum { "dialyzer", "dialyxir_short", "dialyxir_long" }`

 * *Default*: `"dialyzer"`
 
 Formatter to use for Dialyzer warnings

### `elixirLS.dialyzerWarnOpts`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{enum = { "error_handling", "no_behaviours", "no_contracts", "no_fail_call", "no_fun_app", "no_improper_lists", "no_match", "no_missing_calls", "no_opaque", "no_return", "no_undefined_callbacks", "no_unused", "underspecs", "unknown", "unmatched_returns", "overspecs", "specdiffs" },type = "string"}`
 
 Dialyzer options to enable or disable warnings\. See Dialyzer\'s documentation for options\. Note that the \"race\_conditions\" option is unsupported

### `elixirLS.fetchDeps`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Automatically fetch project dependencies when compiling

### `elixirLS.mixEnv`

  * *Type*: `string`

 * *Default*: `"test"`
 
 Mix environment to use for compilation

### `elixirLS.projectDir`

  * *Type*: `string`

 Subdirectory containing Mix project if not in the project root

### `elixirLS.suggestSpecs`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Suggest \@spec annotations inline using Dialyzer\'s inferred success typings \(Requires Dialyzer\)



