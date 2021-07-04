# HTML (html)

https://github.com/hrsh7th/vscode-langservers-extracted

`vscode-html-language-server` can be installed via `npm`:
```sh
npm i -g vscode-langservers-extracted
```

Neovim does not currently include built-in snippets. `vscode-html-language-server` only provides completions when snippet support is enabled.
To enable completion, install a snippet plugin and add the following override to your language client capabilities during setup.

```lua
--Enable (broadcasting) snippet capability for completion
local capabilities = vim.lsp.protocol.make_client_capabilities()
capabilities.textDocument.completion.completionItem.snippetSupport = true

require'lspconfig'.html.setup {
  capabilities = capabilities,
}
```


## Setup

```lua
require'lspconfig'.html.setup{}
```


### Default values

```lua
cmd = { "vscode-html-language-server", "--stdio" }
filetypes = { "html" }
init_options = {
  configurationSection = { "html", "css", "javascript" },
  embeddedLanguages = {
    css = true,
    javascript = true
  }
}
root_dir = function(fname)
      return root_pattern(fname) or vim.loop.os_homedir()
    end,
settings = {}
```




