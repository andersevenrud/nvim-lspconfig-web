# Haxe (haxe_language_server)

https://github.com/vshaxe/haxe-language-server

The Haxe language server can be built by running the following commands from
the project's root directory:

    npm install
    npx lix run vshaxe-build -t language-server

This will create `bin/server.js`. Note that the server requires Haxe 3.4.0 or
higher.

After building the language server, set the `cmd` setting in your setup
function:

```lua
lspconfig.haxe_language_server.setup({
  cmd = {"node", "path/to/bin/server.js"},
})
```

By default, an HXML compiler arguments file named `build.hxml` is expected in
your project's root directory. If your file is named something different,
specify it using the `init_options.displayArguments` setting.


## Setup

```lua
require'lspconfig'.haxe_language_server.setup{}
```


### Default values

```lua
cmd = { "haxe-language-server" }
filetypes = { "haxe" }
init_options = {
  displayArguments = { "build.hxml" }
}
root_dir = root_pattern("*.hxml")
settings = {
  haxe = {
    executable = "haxe"
  }
}
```




