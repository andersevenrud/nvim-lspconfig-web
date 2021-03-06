# Scala (metals)

https://scalameta.org/metals/

Scala language server with rich IDE features.

See full instructions in the Metals documentation:

https://scalameta.org/metals/docs/editors/vim.html#using-an-alternative-lsp-client

Note: that if you're using [nvim-metals](https://github.com/scalameta/nvim-metals), that plugin fully handles the setup and installation of Metals, and you shouldn't set up Metals both with it and this plugin.

To install Metals, make sure to have [coursier](https://get-coursier.io/docs/cli-installation) installed, and once you do you can install the latest Metals with `cs install metals`. You can also manually bootstrap Metals with the following command.

```bash
cs bootstrap \
  --java-opt -Xss4m \
  --java-opt -Xms100m \
  org.scalameta:metals_2.12:<enter-version-here> \
  -r bintray:scalacenter/releases \
  -r sonatype:snapshots \
  -o /usr/local/bin/metals -f
```


## Setup

```lua
require'lspconfig'.metals.setup{}
```


### Default values

```lua
cmd = { "metals" }
filetypes = { "scala" }
init_options = {
  compilerOptions = {
    snippetAutoIndent = false
  },
  isHttpEnabled = true,
  statusBarProvider = "show-message"
}
message_level = 4
root_dir = util.root_pattern("build.sbt", "build.sc", "build.gradle", "pom.xml")
```




