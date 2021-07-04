# Docker (dockerls)

https://github.com/rcjsuen/dockerfile-language-server-nodejs

`docker-langserver` can be installed via `npm`:
```sh
npm install -g dockerfile-language-server-nodejs
```
    

## Setup

```lua
require'lspconfig'.dockerls.setup{}
```


### Default values

```lua
cmd = { "docker-langserver", "--stdio" }
filetypes = { "Dockerfile", "dockerfile" }
root_dir = root_pattern("Dockerfile")
```




