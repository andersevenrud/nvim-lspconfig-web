# OCaml (ocamlls)

https://github.com/ocaml-lsp/ocaml-language-server

`ocaml-language-server` can be installed via `npm`
```sh
npm install -g ocaml-langauge-server
```
    

## Setup

```lua
require'lspconfig'.ocamlls.setup{}
```


### Default values

```lua
cmd = { "ocaml-language-server", "--stdio" }
filetypes = { "ocaml", "reason" }
root_dir = root_pattern("*.opam", "esy.json", "package.json")
```




