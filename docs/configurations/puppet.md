# Puppet (puppet)

LSP server for Puppet.

Installation:

- Clone the editor-services repository:
    https://github.com/puppetlabs/puppet-editor-services

- Navigate into that directory and run: `bundle install`

- Install the 'puppet-lint' gem: `gem install puppet-lint`

- Add that repository to $PATH.

- Ensure you can run `puppet-languageserver` from outside the editor-services directory.


## Setup

```lua
require'lspconfig'.puppet.setup{}
```


### Default values

```lua
cmd = { "puppet-languageserver", "--stdio" }
filetypes = { "puppet" }
root_dir = root_pattern("manifests", ".puppet-lint.rc", "hiera.yaml", ".git")
```




