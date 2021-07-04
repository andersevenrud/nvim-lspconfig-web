# Zig (zls)

           https://github.com/zigtools/zls

           `Zig LSP implementation + Zig Language Server`.
        

## Setup

```lua
require'lspconfig'.zls.setup{}
```


### Default values

```lua
cmd = { "zls" }
filetypes = { "zig", "zir" }
root_dir = util.root_pattern("zls.json", ".git") or current_file_dirname
```




