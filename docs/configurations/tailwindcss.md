# Tailwind (tailwindcss)

https://github.com/tailwindlabs/tailwindcss-intellisense

Tailwind CSS Language Server

**NOTE:** The current tailwindcss-language-server npm package is a different project.

Until the standalone server is published to npm, you can extract the server from the VS Code package:

```bash
curl -L -o tailwindcss-intellisense.vsix https://github.com/tailwindlabs/tailwindcss-intellisense/releases/download/v0.6.8/vscode-tailwindcss-0.6.8.vsix
unzip tailwindcss-intellisense.vsix -d tailwindcss-intellisense
echo "#\!/usr/bin/env node\n$(cat tailwindcss-intellisense/extension/dist/server/tailwindServer.js)" > tailwindcss-language-server
chmod +x tailwindcss-language-server
```

Copy or symlink tailwindcss-language-server to somewhere in your $PATH.

Alternatively, it might be packaged for your operating system, eg.:
https://aur.archlinux.org/packages/tailwindcss-language-server/


## Setup

```lua
require'lspconfig'.tailwindcss.setup{}
```


### Default values

```lua
cmd = { "tailwindcss-language-server", "--stdio" }
filetypes = { "aspnetcorerazor", "astro", "astro-markdown", "blade", "django-html", "edge", "eelixir", "ejs", "erb", "eruby", "gohtml", "haml", "handlebars", "hbs", "html", "html-eex", "jade", "leaf", "liquid", "markdown", "mdx", "mustache", "njk", "nunjucks", "php", "razor", "slim", "twig", "css", "less", "postcss", "sass", "scss", "stylus", "sugarss", "javascript", "javascriptreact", "reason", "rescript", "typescript", "typescriptreact", "vue", "svelte" }
init_options = {
  userLanguages = {
    eelixir = "html-eex",
    eruby = "erb"
  }
}
on_new_config = function(new_config)
      if not new_config.settings then
        new_config.settings = {}
      end
      if not new_config.settings.editor then
        new_config.settings.editor = {}
      end
      if not new_config.settings.editor.tabSize then
        -- set tab size for hover
        new_config.settings.editor.tabSize = vim.lsp.util.get_effective_tabstop()
      end
    end,
root_dir = root_pattern('tailwind.config.js', 'tailwind.config.ts', 'postcss.config.js', 'postcss.config.ts', 'package.json', 'node_modules', '.git')
settings = {
  tailwindCSS = {
    lint = {
      cssConflict = "warning",
      invalidApply = "error",
      invalidConfigPath = "error",
      invalidScreen = "error",
      invalidTailwindDirective = "error",
      invalidVariant = "error",
      recommendedVariantOrder = "warning"
    },
    validate = true
  }
}
```




