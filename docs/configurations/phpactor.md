# PHP (phpactor)

https://github.com/phpactor/phpactor

Installation: https://phpactor.readthedocs.io/en/master/usage/standalone.html#global-installation


## Setup

```lua
require'lspconfig'.phpactor.setup{}
```


### Default values

```lua
cmd = { "phpactor", "language-server" }
filetypes = { "php" }
root_dir = root_pattern("composer.json", ".git")
```




