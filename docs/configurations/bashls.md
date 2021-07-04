# Bash (bashls)

https://github.com/mads-hartmann/bash-language-server

Language server for bash, written using tree sitter in typescript.


## Setup

```lua
require'lspconfig'.bashls.setup{}
```


### Default values

```lua
cmd = { "bash-language-server", "start" }
cmd_env = {
  GLOB_PATTERN = "*@(.sh|.inc|.bash|.command)"
}
filetypes = { "sh" }
root_dir = vim's starting directory
```




