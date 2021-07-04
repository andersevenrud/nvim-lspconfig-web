# Verilog (svls)

      https://github.com/dalance/svls
      Language server for verilog and SystemVerilog
    

## Setup

```lua
require'lspconfig'.svls.setup{}
```


### Default values

```lua
cmd = { "svls" }
filetypes = { "verilog", "systemverilog" }
root_dir = function(startpath)
    return M.search_ancestors(startpath, matcher)
  end
```




