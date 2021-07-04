# Prisma (prismals)

npm install -g @prisma/language-server

'prismals, a language server for the prisma javascript and typescript orm'


## Setup

```lua
require'lspconfig'.prismals.setup{}
```


### Default values

```lua
cmd = { "prisma-language-server", "--stdio" }
filetypes = { "prisma" }
root_dir = root_pattern(".git", "package.json")
settings = {
  prisma = {
    prismaFmtBinPath = ""
  }
}
```




