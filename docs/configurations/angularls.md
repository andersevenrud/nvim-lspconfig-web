# Angular (angularls)

https://github.com/angular/vscode-ng-language-service

`angular-language-server` can be installed via npm `npm install -g @angular/language-server`.

Note, that if you override the default `cmd`, you must also update `on_new_config` to set `new_config.cmd` during startup.

```lua
local project_library_path = "/path/to/project/lib"
local cmd = {"ngserver", "--stdio", "--tsProbeLocations", project_library_path , "--ngProbeLocations", project_library_path}

require'lspconfig'.angularls.setup{
  cmd = cmd,
  on_new_config = function(new_config,new_root_dir)
    new_config.cmd = cmd
  end,
}
```
    

## Setup

```lua
require'lspconfig'.angularls.setup{}
```


### Default values

```lua
cmd = { "ngserver", "--stdio", "--tsProbeLocations", "", "--ngProbeLocations", "" }
filetypes = { "typescript", "html", "typescriptreact", "typescript.tsx" }
root_dir = root_pattern("angular.json", ".git")
```




