# PHP (intelephense)

https://intelephense.com/

`intelephense` can be installed via `npm`:
```sh
npm install -g intelephense
```


## Setup

```lua
require'lspconfig'.intelephense.setup{}
```


### Default values

```lua
cmd = { "intelephense", "--stdio" }
filetypes = { "php" }
root_dir = root_pattern("composer.json", ".git")
```




