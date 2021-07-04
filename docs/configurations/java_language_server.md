# Java (java_language_server)

https://github.com/georgewfraser/java-language-server

Java language server

Point `cmd` to `lang_server_linux.sh` or the equivalent script for macOS/Windows provided by java-language-server


## Setup

```lua
require'lspconfig'.java_language_server.setup{}
```


### Default values

```lua
cmd = {}
filetypes = { "java" }
root_dir = function(startpath)
    return M.search_ancestors(startpath, matcher)
  end
settings = {}
```




