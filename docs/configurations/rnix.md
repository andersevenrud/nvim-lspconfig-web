# Nix (rnix)

https://github.com/nix-community/rnix-lsp

A language server for Nix providing basic completion and formatting via nixpkgs-fmt.

To install manually, run `cargo install rnix-lsp`. If you are using nix, rnix-lsp is in nixpkgs.

This server accepts configuration via the `settings` key.

    

## Setup

```lua
require'lspconfig'.rnix.setup{}
```


### Default values

```lua
cmd = { "rnix-lsp" }
filetypes = { "nix" }
init_options = {}
root_dir = vim's starting directory
settings = {}
```




