# TexLab (texlab)

https://github.com/latex-lsp/texlab

A completion engine built from scratch for (La)TeX.

See https://github.com/latex-lsp/texlab/blob/master/docs/options.md for configuration options.


## Setup

```lua
require'lspconfig'.texlab.setup{}
```

### Commands

- TexlabBuild: Build the current buffer
- TexlabForward: Forward search from current position

### Default values

```lua
cmd = { "texlab" }
filetypes = { "tex", "bib" }
root_dir = vim's starting directory
settings = {
  texlab = {
    auxDirectory = ".",
    bibtexFormatter = "texlab",
    build = {
      args = { "-pdf", "-interaction=nonstopmode", "-synctex=1", "%f" },
      executable = "latexmk",
      forwardSearchAfter = false,
      onSave = false
    },
    chktex = {
      onEdit = false,
      onOpenAndSave = false
    },
    diagnosticsDelay = 300,
    formatterLineLength = 80,
    forwardSearch = {
      args = {}
    },
    latexFormatter = "latexindent",
    latexindent = {
      modifyLineBreaks = false
    }
  }
}
```




