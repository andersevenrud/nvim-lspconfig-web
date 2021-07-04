# Crystal (scry)

https://github.com/crystal-lang-tools/scry

Crystal language server.


## Setup

```lua
require'lspconfig'.scry.setup{}
```


### Default values

```lua
cmd = { "scry" }
filetypes = { "crystal" }
root_dir = root_pattern('shard.yml', '.git') or dirname
```




