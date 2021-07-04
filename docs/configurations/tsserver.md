# TypeScript (tsserver)

https://github.com/theia-ide/typescript-language-server

`typescript-language-server` depends on `typescript`. Both packages can be installed via `npm`:
```sh
npm install -g typescript typescript-language-server
```


## Setup

```lua
require'lspconfig'.tsserver.setup{}
```


### Default values

```lua
cmd = { "typescript-language-server", "--stdio" }
filetypes = { "javascript", "javascriptreact", "javascript.jsx", "typescript", "typescriptreact", "typescript.tsx" }
root_dir = root_pattern("package.json", "tsconfig.json", "jsconfig.json", ".git")
```




