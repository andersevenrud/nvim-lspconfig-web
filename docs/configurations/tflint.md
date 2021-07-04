# Terraform (tflint)

https://github.com/terraform-linters/tflint

A pluggable Terraform linter that can act as lsp server.
Installation instructions can be found in https://github.com/terraform-linters/tflint#installation.


## Setup

```lua
require'lspconfig'.tflint.setup{}
```


### Default values

```lua
cmd = { "tflint", "--langserver" }
filetypes = { "terraform" }
root_dir = root_pattern(".terraform", ".git", ".tflint.hcl")
```




