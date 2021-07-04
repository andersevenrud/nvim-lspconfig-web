# Beancount (beancount)

https://github.com/polarmutex/beancount-language-server#installation

See https://github.com/polarmutex/beancount-language-server#configuration for configuration options


## Setup

```lua
require'lspconfig'.beancount.setup{}
```


### Default values

```lua
cmd = { "beancount-langserver" }
filetypes = { "beancount" }
init_options = {
  journalFile = "",
  pythonPath = "python3"
}
root_dir = root_pattern("elm.json")
```




