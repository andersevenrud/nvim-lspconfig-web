# Go (gopls)

https://github.com/golang/tools/tree/master/gopls

Google's lsp server for golang.


## Setup

```lua
require'lspconfig'.gopls.setup{}
```


### Default values

```lua
cmd = { "gopls" }
filetypes = { "go", "gomod" }
root_dir = root_pattern("go.mod", ".git")
```




