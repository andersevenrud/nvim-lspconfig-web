# C# (omnisharp)

https://github.com/omnisharp/omnisharp-roslyn
OmniSharp server based on Roslyn workspaces

`omnisharp-roslyn` can be installed by downloading and extracting a release from [here](https://github.com/OmniSharp/omnisharp-roslyn/releases).
Omnisharp can also be built from source by following the instructions [here](https://github.com/omnisharp/omnisharp-roslyn#downloading-omnisharp).

Omnisharp requires the [dotnet-sdk](https://dotnet.microsoft.com/download) to be installed.

**By default, omnisharp-roslyn doesn't have a `cmd` set.** This is because nvim-lspconfig does not make assumptions about your path. You must add the following to your init.vim or init.lua to set `cmd` to the absolute path ($HOME and ~ are not expanded) of the unzipped run script or binary.

```lua
local pid = vim.fn.getpid()
-- On linux/darwin if using a release build, otherwise under scripts/OmniSharp(.Core)(.cmd)
local omnisharp_bin = "/path/to/omnisharp-repo/run"
-- on Windows
-- local omnisharp_bin = "/path/to/omnisharp/OmniSharp.exe"
require'lspconfig'.omnisharp.setup{
    cmd = { omnisharp_bin, "--languageserver" , "--hostPID", tostring(pid) };
    ...
}
```

Note, if you download the executable for darwin you will need to strip the quarantine label to run:
```bash
find /path/to/omnisharp-osx | xargs xattr -r -d com.apple.quarantine
```


## Setup

```lua
require'lspconfig'.omnisharp.setup{}
```


### Default values

```lua
filetypes = { "cs", "vb" }
init_options = {}
root_dir = root_pattern(".csproj", ".sln")
```




