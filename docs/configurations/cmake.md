# CMake (cmake)

https://github.com/regen100/cmake-language-server

CMake LSP Implementation


## Setup

```lua
require'lspconfig'.cmake.setup{}
```


### Default values

```lua
cmd = { "cmake-language-server" }
filetypes = { "cmake" }
init_options = {
  buildDirectory = "build"
}
root_dir = root_pattern(".git", "compile_commands.json", "build") or dirname
```




