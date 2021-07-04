# VimScript (vimls)

https://github.com/iamcco/vim-language-server

You can install vim-language-server via npm:
```sh
npm install -g vim-language-server
```


## Setup

```lua
require'lspconfig'.vimls.setup{}
```


### Default values

```lua
cmd = { "vim-language-server", "--stdio" }
filetypes = { "vim" }
init_options = {
  diagnostic = {
    enable = true
  },
  indexes = {
    count = 3,
    gap = 100,
    projectRootPatterns = { "runtime", "nvim", ".git", "autoload", "plugin" },
    runtimepath = true
  },
  iskeyword = "@,48-57,_,192-255,-#",
  runtimepath = "",
  suggest = {
    fromRuntimepath = true,
    fromVimruntime = true
  },
  vimruntime = ""
}
root_dir = function(fname)
      return util.find_git_ancestor(fname) or vim.fn.getcwd()
    end,
```




