# OCaml (ocamllsp)

https://github.com/ocaml/ocaml-lsp

`ocaml-lsp` can be installed as described in [installation guide](https://github.com/ocaml/ocaml-lsp#installation).

To install the lsp server in a particular opam switch:
```sh
opam pin add ocaml-lsp-server https://github.com/ocaml/ocaml-lsp.git
opam install ocaml-lsp-server
```
    

## Setup

```lua
require'lspconfig'.ocamllsp.setup{}
```


### Default values

```lua
cmd = { "ocamllsp" }
filetypes = { "ocamllex", "menhir", "ocamlinterface", "ocaml", "reason" }
get_language_id = function(_, ftype)
  return language_id_of[ftype]
end
root_dir = root_pattern("*.opam", "esy.json", "package.json", ".git")
```




