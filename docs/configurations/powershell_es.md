# Powershell (powershell_es)

https://github.com/PowerShell/PowerShellEditorServices

Language server for PowerShell.

To install, download and extract PowerShellEditorServices.zip
from the [releases](https://github.com/PowerShell/PowerShellEditorServices/releases).
To configure the language server, set the property `bundle_path` to the root
of the extracted PowerShellEditorServices.zip.

The default configuration doesn't set `cmd` unless `bundle_path` is specified.

```lua
require'lspconfig'.powershell_es.setup{
  bundle_path = 'c:/w/PowerShellEditorServices',
}
```

If necessary, specific `cmd` can be defined instead of `bundle_path`.
See [PowerShellEditorServices](https://github.com/PowerShell/PowerShellEditorServices#stdio)
to learn more.

```lua
require'lspconfig'.powershell_es.setup{
  cmd = {'pwsh', '-NoLogo', '-NoProfile', '-Command', "c:/PSES/Start-EditorServices.ps1 ..."}
}
```


## Setup

```lua
require'lspconfig'.powershell_es.setup{}
```


### Default values

```lua
filetypes = { "ps1" }
on_new_config = function(new_config, _)
      local bundle_path = new_config.bundle_path
      new_config.cmd = make_cmd(bundle_path)
    end,
root_dir = git root or current directory
```




