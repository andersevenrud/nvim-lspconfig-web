# Python (jedi_language_server)

https://github.com/pappasam/jedi-language-server

`jedi-language-server`, a language server for Python, built on top of jedi
    

## Setup

```lua
require'lspconfig'.jedi_language_server.setup{}
```


### Default values

```lua
cmd = { "jedi-language-server" }
filetypes = { "python" }
root_dir = vim's starting directory
```




