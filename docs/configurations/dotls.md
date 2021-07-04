# DOT (dotls)

https://github.com/nikeee/dot-language-server

`dot-language-server` can be installed via `npm`:
```sh
npm install -g dot-language-server
```
    

## Setup

```lua
require'lspconfig'.dotls.setup{}
```


### Default values

```lua
cmd = { "dot-language-server", "--stdio" }
filetypes = { "dot" }
root_dir = function(filename)
      return util.root_pattern(unpack(root_files))(filename) or util.path.dirname(filename)
    end,
```




