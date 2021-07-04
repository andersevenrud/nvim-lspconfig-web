# TypeScript (denols)

https://github.com/denoland/deno

Deno's built-in language server


## Setup

```lua
require'lspconfig'.denols.setup{}
```

### Commands

- DenolsCache: Cache a module and all of its dependencies.
- DenolsDefinition: Jump to definition. This handle deno:/ schema in deno:// buffer.
- DenolsReferences: List references. This handle deno:/ schema in deno:// buffer.

### Default values

```lua
cmd = { "deno", "lsp" }
filetypes = { "javascript", "javascriptreact", "javascript.jsx", "typescript", "typescriptreact", "typescript.tsx" }
handlers = {
  ["textDocument/definition"] = <function 1>,
  ["textDocument/references"] = <function 1>
}
init_options = {
  enable = true,
  lint = false,
  unstable = false
}
root_dir = root_pattern("package.json", "tsconfig.json", ".git")
```




