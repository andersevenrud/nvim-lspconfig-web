# Vala (vala_ls)

https://github.com/benwaffle/vala-language-server

## Setup

```lua
require'lspconfig'.vala_ls.setup{}
```


### Default values

```lua
cmd = { "vala-language-server" }
filetypes = { "vala", "genie" }
root_dir = root_pattern("meson.build", ".git")
```




