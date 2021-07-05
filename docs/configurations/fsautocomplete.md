# F# (fsautocomplete)

https://github.com/fsharp/FsAutoComplete

Language Server for F# provided by FsAutoComplete (FSAC).

FsAutoComplete requires the [dotnet-sdk](https://dotnet.microsoft.com/download) to be installed.

The prefered way to install FsAutoComplete is with `dotnet tool install --global fsautocomplete`.

Instructions to compile from source are found on the main [repository](https://github.com/fsharp/FsAutoComplete).

You may also need to configure the filetype as Vim defaults to Forth for `*.fs` files:

`autocmd BufNewFile,BufRead *.fs,*.fsx,*.fsi set filetype=fsharp`

This is automatically done by plugins such as [PhilT/vim-fsharp](https://github.com/PhilT/vim-fsharp), [fsharp/vim-fsharp](https://github.com/fsharp/vim-fsharp), and [adelarsq/neofsharp.vim](https://github.com/adelarsq/neofsharp.vim).

    

## Setup

```lua
require'lspconfig'.fsautocomplete.setup{}
```


### Default values

```lua
cmd = { "dotnet", "fsautocomplete", "--background-service-enabled" }
filetypes = { "fsharp" }
init_options = {
  AutomaticWorkspaceInit = true
}
root_dir = function(startpath)
    return M.search_ancestors(startpath, matcher)
  end
```




