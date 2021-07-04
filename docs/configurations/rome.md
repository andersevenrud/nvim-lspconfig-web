# TypeScript (rome)

https://rome.tools

Language server for the Rome Frontend Toolchain.

```sh
npm install [-g] rome
```


## Setup

```lua
require'lspconfig'.rome.setup{}
```


### Default values

```lua
cmd = { "rome", "lsp" }
filetypes = { "javascript", "javascriptreact", "json", "typescript", "typescript.tsx", "typescriptreact" }
root_dir = root_pattern('package.json', 'node_modules', '.git') or dirname
```




