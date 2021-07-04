# Haskell (ghcide)

https://github.com/digital-asset/ghcide

A library for building Haskell IDE tooling.
"ghcide" isn't for end users now. Use "haskell-language-server" instead of "ghcide".


## Setup

```lua
require'lspconfig'.ghcide.setup{}
```


### Default values

```lua
cmd = { "ghcide", "--lsp" }
filetypes = { "haskell", "lhaskell" }
root_dir = root_pattern("stack.yaml", "hie-bios", "BUILD.bazel", "cabal.config", "package.yaml")
```




