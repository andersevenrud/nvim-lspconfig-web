# Perl (perlls)

https://github.com/richterger/Perl-LanguageServer/tree/master/clients/vscode/perl

`Perl-LanguageServer`, a language server for Perl.

To use the language server, ensure that you have Perl::LanguageServer installed and perl command is on your path.


## Setup

```lua
require'lspconfig'.perlls.setup{}
```


### Default values

```lua
cmd = { "perl", "-MPerl::LanguageServer", "-e", "Perl::LanguageServer::run", "--", "--port 13603", "--nostdio 0", "--version 2.1.0" }
filetypes = { "perl" }
root_dir = vim's starting directory
settings = {
  perl = {
    fileFilter = { ".pm", ".pl" },
    ignoreDirs = ".git",
    perlCmd = "perl",
    perlInc = " "
  }
}
```


This server accepts configuration via the `settings` key.

## Available settings

### `perl.debugAdapterPort`

  * *Type*: `string`

 * *Default*: `"13603"`
 
 port to use for connection between vscode and debug adapter inside Perl\:\:LanguageServer\. On a multi user system every user must use a different port\.

### `perl.disableCache`

  * *Type*: `boolean`

 if true\, the LanguageServer will not cache the result of parsing source files on disk\, so it can be used within readonly directories

### `perl.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 enable\/disable this extension

### `perl.fileFilter`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 array for filtering perl file\, defaults to \*\.pm|\*\.pl

### `perl.ignoreDirs`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 directories to ignore\, defaults to \.vscode\, \.git\, \.svn

### `perl.logFile`

  * *Type*: `string`

 * *Default*: `vim.NIL`
 
 If set\, log output is written to the given logfile\, instead of displaying it in the vscode output pane\. Log output is always appended so you are responsible for rotating the file\.

### `perl.logLevel`

  * *Type*: `integer`

 * *Default*: `0`
 
 Log level 0\-2

### `perl.pathMap`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 mapping of local to remote paths

### `perl.perlCmd`

  * *Type*: `string`

 * *Default*: `vim.NIL`
 
 defaults to perl

### `perl.perlInc`

  * *Type*: `array`

 * *Default*: `vim.NIL`
 
 array with paths to add to perl library path\. This setting is used by the syntax checker and for the debugee and also for the LanguageServer itself\.

### `perl.showLocalVars`

  * *Type*: `boolean`

 if true\, show also local variables in symbol view

### `perl.sshAddr`

  * *Type*: `string`

 * *Default*: `vim.NIL`
 
 ip address of remote system

### `perl.sshArgs`

  * *Type*: `string`

 * *Default*: `vim.NIL`
 
 optional arguments for ssh

### `perl.sshCmd`

  * *Type*: `string`

 * *Default*: `vim.NIL`
 
 defaults to ssh on unix and plink on windows

### `perl.sshPort`

  * *Type*: `string`

 * *Default*: `vim.NIL`
 
 optional\, port for ssh to remote system

### `perl.sshUser`

  * *Type*: `string`

 * *Default*: `vim.NIL`
 
 user for ssh login

### `perl.sshWorkspaceRoot`

  * *Type*: `string`

 * *Default*: `vim.NIL`
 
 path of the workspace root on remote system



