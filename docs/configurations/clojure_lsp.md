# Clojure (clojure_lsp)

https://github.com/snoe/clojure-lsp

Clojure Language Server


## Setup

```lua
require'lspconfig'.clojure_lsp.setup{}
```


### Default values

```lua
cmd = { "clojure-lsp" }
filetypes = { "clojure", "edn" }
root_dir = root_pattern("project.clj", "deps.edn", ".git")
```




