# C like (clangd)

https://clangd.llvm.org/installation.html

**NOTE:** Clang >= 9 is recommended! See [this issue for more](https://github.com/neovim/nvim-lsp/issues/23).

clangd relies on a [JSON compilation database](https://clang.llvm.org/docs/JSONCompilationDatabase.html) specified
as compile_commands.json or, for simpler projects, a compile_flags.txt.
For details on how to automatically generate one using CMake look [here](https://cmake.org/cmake/help/latest/variable/CMAKE_EXPORT_COMPILE_COMMANDS.html).


## Setup

```lua
require'lspconfig'.clangd.setup{}
```

### Commands

- ClangdSwitchSourceHeader: Switch between source/header

### Default values

```lua
capabilities = default capabilities, with offsetEncoding utf-8
cmd = { "clangd", "--background-index" }
filetypes = { "c", "cpp", "objc", "objcpp" }
on_init = function to handle changing offsetEncoding
root_dir = root_pattern("compile_commands.json", "compile_flags.txt", ".git") or dirname
```




