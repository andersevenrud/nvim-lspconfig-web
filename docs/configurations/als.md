# Ada (als)

https://github.com/AdaCore/ada_language_server

Installation instructions can be found [here](https://github.com/AdaCore/ada_language_server#Install).

Can be configured by passing a "settings" object to `als.setup{}`:

```lua
require('lspconfig').als.setup{
    settings = {
      ada = {
        projectFile = "project.gpr";
        scenarioVariables = { ... };
      }
    }
}
```


## Setup

```lua
require'lspconfig'.als.setup{}
```


### Default values

```lua
cmd = { "ada_language_server" }
filetypes = { "ada" }
root_dir = util.root_pattern("Makefile", ".git")
```




