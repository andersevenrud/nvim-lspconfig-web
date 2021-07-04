# dhall_lsp_server



## Setup

```lua
require'lspconfig'.dhall_lsp_server.setup{}
```


### Default values

```lua
cmd = { "dhall-lsp-server" }
docs = {
  default_config = {
    language_name = "Dhall",
    root_dir = 'root_pattern(".git", vim.fn.getcwd())'
  },
  description = "https://github.com/dhall-lang/dhall-haskell/tree/master/dhall-lsp-server\n\nlanguage server for dhall\n\n`dhall-lsp-server` can be installed via cabal:\n```sh\ncabal install dhall-lsp-server\n```\nprebuilt binaries can be found [here](https://github.com/dhall-lang/dhall-haskell/releases).\n"
}
filetypes = { "dhall" }
root_dir = function(startpath)
    return M.search_ancestors(startpath, matcher)
  end
```




