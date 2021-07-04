# CodeQL (codeqlls)

Reference:
https://help.semmle.com/codeql/codeql-cli.html

Binaries:
https://github.com/github/codeql-cli-binaries
        

## Setup

```lua
require'lspconfig'.codeqlls.setup{}
```


### Default values

```lua
before_init = function(initialize_params)
      initialize_params["workspaceFolders"] = {
        {
          name = "workspace",
          uri = initialize_params["rootUri"],
        },
      }
    end,
cmd = { "codeql", "execute", "language-server", "--check-errors", "ON_CHANGE", "-q" }
filetypes = { "ql" }
log_level = 2
root_dir = function(fname)
      return root_pattern(fname) or util.path.dirname(fname)
    end,
settings = {
  search_path = "list containing all search paths, eg: '~/codeql-home/codeql-repo'"
}
```




