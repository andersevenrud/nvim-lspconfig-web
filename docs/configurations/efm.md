# Diagnostics (efm)

https://github.com/mattn/efm-langserver

General purpose Language Server that can use specified error message format generated from specified command.


## Setup

```lua
require'lspconfig'.efm.setup{}
```


### Default values

```lua
cmd = { "efm-langserver" }
root_dir = util.root_pattern(".git")(fname) or util.path.dirname(fname)
```




