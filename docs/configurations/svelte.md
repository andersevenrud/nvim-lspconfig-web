# Svelte (svelte)

https://github.com/sveltejs/language-tools/tree/master/packages/language-server

`svelte-language-server` can be installed via `npm`:
```sh
npm install -g svelte-language-server
```


## Setup

```lua
require'lspconfig'.svelte.setup{}
```


### Default values

```lua
cmd = { "svelteserver", "--stdio" }
filetypes = { "svelte" }
root_dir = root_pattern("package.json", ".git")
```




