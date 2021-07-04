# Vue (vuels)

https://github.com/vuejs/vetur/tree/master/server

Vue language server(vls)
`vue-language-server` can be installed via `npm`:
```sh
npm install -g vls
```


## Setup

```lua
require'lspconfig'.vuels.setup{}
```


### Default values

```lua
cmd = { "vls" }
filetypes = { "vue" }
init_options = {
  config = {
    css = {},
    emmet = {},
    html = {
      suggest = {}
    },
    javascript = {
      format = {}
    },
    stylusSupremacy = {},
    typescript = {
      format = {}
    },
    vetur = {
      completion = {
        autoImport = false,
        tagCasing = "kebab",
        useScaffoldSnippets = false
      },
      format = {
        defaultFormatter = {
          js = "none",
          ts = "none"
        },
        defaultFormatterOptions = {},
        scriptInitialIndent = false,
        styleInitialIndent = false
      },
      useWorkspaceDependencies = false,
      validation = {
        script = true,
        style = true,
        template = true
      }
    }
  }
}
root_dir = root_pattern("package.json", "vue.config.js")
```


This server accepts configuration via the `settings` key.

## Available settings

### `vetur.completion.autoImport`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Include completion for module export and auto import them

### `vetur.completion.scaffoldSnippetSources`

  * *Type*: `object`

 * *Default*: `{user = "🗒️",vetur = "✌",workspace = "💼"}`
 
 Where Vetur source Scaffold Snippets from and how to indicate them\. Set a source to \"\" to disable it\.
 
 \- workspace\: \`\<WORKSPACE\>\/\.vscode\/vetur\/snippets\`\.
 \- user\: \`\<USER\-DATA\-DIR\>\/User\/snippets\/vetur\`\.
 \- vetur\: Bundled in Vetur\.
 
 The default is\:
 \`\`\`
 \"vetur\.completion\.scaffoldSnippetSources\"\: \{
   \"workspace\"\: \"💼\"\,
   \"user\"\: \"🗒️\"\,
   \"vetur\"\: \"✌\"
 \}
 \`\`\`
 
 Alternatively\, you can do\:
 
 \`\`\`
 \"vetur\.completion\.scaffoldSnippetSources\"\: \{
   \"workspace\"\: \"\(W\)\"\,
   \"user\"\: \"\(U\)\"\,
   \"vetur\"\: \"\(V\)\"
 \}
 \`\`\`
 
 Read more\: https\:\/\/vuejs\.github\.io\/vetur\/snippet\.html\.

### `vetur.completion.tagCasing`

  `enum { "initial", "kebab" }`

 * *Default*: `"kebab"`
 
 Casing conversion for tag completion

### `vetur.dev.logLevel`

  `enum { "INFO", "DEBUG" }`

 * *Default*: `"INFO"`
 
 Log level for VLS

### `vetur.dev.vlsPath`

  * *Type*: `string`

 Path to vls for Vetur developers\. There are two ways of using it\. 
 
 1\. Clone vuejs\/vetur from GitHub\, build it and point it to the ABSOLUTE path of \`\/server\`\.
 2\. \`yarn global add vls\` and point Vetur to the installed location \(\`yarn global dir\` + node\_modules\/vls\)

### `vetur.dev.vlsPort`

  * *Type*: `number`

 * *Default*: `-1`
 
 The port that VLS listens to\. Can be used for attaching to the VLS Node process for debugging \/ profiling\.

### `vetur.experimental.templateInterpolationService`

  * *Type*: `boolean`

 Enable template interpolation service that offers hover \/ definition \/ references in Vue interpolations\.

### `vetur.format.defaultFormatter.css`

  `enum { "none", "prettier" }`

 * *Default*: `"prettier"`
 
 Default formatter for \<style\> region

### `vetur.format.defaultFormatter.html`

  `enum { "none", "prettyhtml", "js-beautify-html", "prettier" }`

 * *Default*: `"prettier"`
 
 Default formatter for \<template\> region

### `vetur.format.defaultFormatter.js`

  `enum { "none", "prettier", "prettier-eslint", "vscode-typescript" }`

 * *Default*: `"prettier"`
 
 Default formatter for \<script\> region

### `vetur.format.defaultFormatter.less`

  `enum { "none", "prettier" }`

 * *Default*: `"prettier"`
 
 Default formatter for \<style lang\=\'less\'\> region

### `vetur.format.defaultFormatter.postcss`

  `enum { "none", "prettier" }`

 * *Default*: `"prettier"`
 
 Default formatter for \<style lang\=\'postcss\'\> region

### `vetur.format.defaultFormatter.pug`

  `enum { "none", "prettier" }`

 * *Default*: `"prettier"`
 
 Default formatter for \<template lang\=\'pug\'\> region

### `vetur.format.defaultFormatter.sass`

  `enum { "none", "sass-formatter" }`

 * *Default*: `"sass-formatter"`
 
 Default formatter for \<style lang\=\'sass\'\> region

### `vetur.format.defaultFormatter.scss`

  `enum { "none", "prettier" }`

 * *Default*: `"prettier"`
 
 Default formatter for \<style lang\=\'scss\'\> region

### `vetur.format.defaultFormatter.stylus`

  `enum { "none", "stylus-supremacy" }`

 * *Default*: `"stylus-supremacy"`
 
 Default formatter for \<style lang\=\'stylus\'\> region

### `vetur.format.defaultFormatter.ts`

  `enum { "none", "prettier", "prettier-tslint", "vscode-typescript" }`

 * *Default*: `"prettier"`
 
 Default formatter for \<script\> region

### `vetur.format.defaultFormatterOptions`

  * *Type*: `object`

 * *Default*: `{["js-beautify-html"] = {wrap_attributes = "force-expand-multiline"},prettyhtml = {printWidth = 100,singleQuote = false,sortAttributes = false,wrapAttributes = false}}`
 
 Options for all default formatters

### `vetur.format.enable`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable\/disable the Vetur document formatter\.

### `vetur.format.options.tabSize`

  * *Type*: `number`

 * *Default*: `2`
 
 Number of spaces per indentation level\. Inherited by all formatters\.

### `vetur.format.options.useTabs`

  * *Type*: `boolean`

 Use tabs for indentation\. Inherited by all formatters\.

### `vetur.format.scriptInitialIndent`

  * *Type*: `boolean`

 Whether to have initial indent for \<script\> region

### `vetur.format.styleInitialIndent`

  * *Type*: `boolean`

 Whether to have initial indent for \<style\> region

### `vetur.grammar.customBlocks`

  * *Type*: `object`

 * *Default*: `{docs = "md",i18n = "json"}`
 
 Mapping from custom block tag name to language name\. Used for generating grammar to support syntax highlighting for custom blocks\.

### `vetur.ignoreProjectWarning`

  * *Type*: `boolean`

 Vetur will warn about not setup correctly for the project\. You can disable it\.

### `vetur.languageFeatures.codeActions`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to enable codeActions

### `vetur.languageFeatures.semanticTokens`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to enable semantic highlighting\. Currently only works for typescript

### `vetur.languageFeatures.updateImportOnFileMove`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether to automatic updating import path when rename or move a file

### `vetur.trace.server`

  `enum { "off", "messages", "verbose" }`

 * *Default*: `"off"`
 
 Traces the communication between VS Code and Vue Language Server\.

### `vetur.underline.refValue`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Enable underline \`\.value\` when using composition API\.

### `vetur.useWorkspaceDependencies`

  * *Type*: `boolean`

 Use dependencies from workspace\. Currently only for TypeScript\.

### `vetur.validation.interpolation`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Validate interpolations in \<template\> region using TypeScript language service

### `vetur.validation.script`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Validate js\/ts in \<script\>

### `vetur.validation.style`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Validate css\/scss\/less\/postcss in \<style\>

### `vetur.validation.template`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Validate vue\-html in \<template\> using eslint\-plugin\-vue

### `vetur.validation.templateProps`

  * *Type*: `boolean`

 Validate props usage in \<template\> region\. Show error\/warning for not passing declared props to child components and show error for passing wrongly typed interpolation expressions



