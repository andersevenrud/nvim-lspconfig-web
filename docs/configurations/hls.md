# Haskell (hls)

https://github.com/haskell/haskell-language-server

Haskell Language Server
        

## Setup

```lua
require'lspconfig'.hls.setup{}
```


### Default values

```lua
cmd = { "haskell-language-server-wrapper", "--lsp" }
filetypes = { "haskell", "lhaskell" }
lspinfo = function(cfg)
      -- return "specific"
      if cfg.settings.languageServerHaskell.logFile or false then
        return "logfile: " .. cfg.settings.languageServerHaskell.logFile
      end
      return ""
    end,
root_dir = root_pattern("*.cabal", "stack.yaml", "cabal.project", "package.yaml", "hie.yaml")
settings = {
  languageServerHaskell = {
    formattingProvider = "ormolu"
  }
}
```




