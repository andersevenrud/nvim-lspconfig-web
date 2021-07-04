# GraphQL (graphql)

https://github.com/graphql/graphiql/tree/main/packages/graphql-language-service-cli

`graphql-lsp` can be installed via `npm`:

```sh
npm install -g graphql-language-service-cli
```


## Setup

```lua
require'lspconfig'.graphql.setup{}
```


### Default values

```lua
cmd = { "graphql-lsp", "server", "-m", "stream" }
filetypes = { "graphql" }
root_dir = root_pattern('.git', '.graphqlrc')
```




