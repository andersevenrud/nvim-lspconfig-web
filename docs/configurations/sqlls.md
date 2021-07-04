# SQL (sqlls)

https://github.com/joe-re/sql-language-server

`cmd` value is **not set** by default. The `cmd` value can be overriden in the `setup` table;

```lua
require'lspconfig'.sqlls.setup{
  cmd = {"path/to/command", "up", "--method", "stdio"};
  ...
}
```

This LSP can be installed via  `npm`. Find further instructions on manual installation of the sql-language-server at [joe-re/sql-language-server](https://github.com/joe-re/sql-language-server).
<br>
    

## Setup

```lua
require'lspconfig'.sqlls.setup{}
```


### Default values

```lua
filetypes = { "sql", "mysql" }
root_dir = function(fname)
      return root_pattern(fname) or vim.loop.os_homedir()
    end,
settings = {}
```




