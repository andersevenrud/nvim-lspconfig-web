# Terraform (terraformls)

https://github.com/hashicorp/terraform-ls

Terraform language server
Download a released binary from https://github.com/hashicorp/terraform-ls/releases.


## Setup

```lua
require'lspconfig'.terraformls.setup{}
```


### Default values

```lua
cmd = { "terraform-ls", "serve" }
filetypes = { "terraform" }
root_dir = root_pattern(".terraform", ".git")
```


This server accepts configuration via the `settings` key.

## Available settings

### `terraform-ls.excludeRootModules`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 Per\-workspace list of module directories for the language server to exclude

### `terraform-ls.experimentalFeatures`

  * *Type*: `object`

 Experimental \(opt\-in\) terraform\-ls features

### `terraform-ls.rootModules`

  * *Type*: `array`

 * *Default*: `{}`
 
 * *Array items*: `{type = "string"}`
 
 Per\-workspace list of module directories for the language server to read

### `terraform.languageServer`

  * *Type*: `object`

 * *Default*: `{args = { "serve" },external = true,maxNumberOfProblems = 100,pathToBinary = "",["trace.server"] = "off"}`
 
 Language Server settings



