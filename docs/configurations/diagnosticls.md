# Diagnostics (diagnosticls)

https://github.com/iamcco/diagnostic-languageserver

Diagnostic language server integrate with linters.


## Setup

```lua
require'lspconfig'.diagnosticls.setup{}
```


### Default values

```lua
cmd = { "diagnostic-languageserver", "--stdio" }
filetypes = Empty by default, override to add filetypes
root_dir = Vim's starting directory
```




