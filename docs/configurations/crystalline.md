# Crystal (crystalline)

https://github.com/elbywan/crystalline

Crystal language server.


## Setup

```lua
require'lspconfig'.crystalline.setup{}
```


### Default values

```lua
cmd = { "crystalline" }
filetypes = { "crystal" }
root_dir = root_pattern('shard.yml', '.git') or dirname
```




