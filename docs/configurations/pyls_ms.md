# Python (pyls_ms)

https://github.com/Microsoft/python-language-server

`python-language-server`, a language server for Python.

Requires [.NET Core](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-install-script) to run. On Linux or macOS:

```bash
curl -L https://dot.net/v1/dotnet-install.sh | sh
```

`python-language-server` can be installed via [build](https://github.com/microsoft/python-language-server/blob/master/CONTRIBUTING.md#setup).

Set cmd to point to `Microsoft.Python.languageServer.dll`.

```lua
cmd = { "dotnet", "exec", "path/to/Microsoft.Python.languageServer.dll" };
```

If the `python` interpreter is not in your PATH environment variable, set the `InterpreterPath` and `Version` properties accordingly.

```lua
InterpreterPath = "path/to/python",
Version = "3.8"
```

This server accepts configuration via the `settings` key.

    

## Setup

```lua
require'lspconfig'.pyls_ms.setup{}
```


### Default values

```lua
filetypes = { "python" }
init_options = {
  analysisUpdates = true,
  asyncStartup = true,
  displayOptions = {},
  interpreter = {
    properties = {
      InterpreterPath = "",
      Version = ""
    }
  }
}
root_dir = vim's starting directory
settings = {
  python = {
    analysis = {
      disabled = {},
      errors = {},
      info = {}
    }
  }
}
```




