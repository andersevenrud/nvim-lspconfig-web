# Lean (leanls)

https://github.com/leanprover/lean4

Lean installation instructions can be found
[here](https://leanprover-community.github.io/get_started.html#regular-install).

The Lean 4 language server is built-in with a Lean 4 install
(and can be manually run with, e.g., `lean --server`).
    

## Setup

```lua
require'lspconfig'.leanls.setup{}
```


### Default values

```lua
cmd = { "lean", "--server" }
filetypes = { "lean" }
on_new_config = function(config, root)
      if not util.path.is_file(root .. "/leanpkg.toml") then
        return
      end
      if not config.cmd_cwd then
        config.cmd_cwd = root
      end
    end,
root_dir = root_pattern("leanpkg.toml") or root_pattern(".git") or path.dirname
```




