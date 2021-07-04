# Kotlin (kotlin_language_server)

    A kotlin language server which was developed for internal usage and
    released afterwards. Maintaining is not done by the original author,
    but by fwcd.

    It is builded via gradle and developed on github.
    Source and additional description:
    https://github.com/fwcd/kotlin-language-server
    

## Setup

```lua
require'lspconfig'.kotlin_language_server.setup{}
```


### Default values

```lua
cmd = { "kotlin-language-server" }
filetypes = { "kotlin" }
root_dir = root_pattern("settings.gradle")
```


This server accepts configuration via the `settings` key.

## Available settings

### `kotlin.compiler.jvm.target`

  * *Type*: `string`

 * *Default*: `"default"`
 
 Specifies the JVM target\, e\.g\. \"1\.6\" or \"1\.8\"

### `kotlin.completion.snippets.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Specifies whether code completion should provide snippets \(true\) or plain\-text items \(false\)\.

### `kotlin.debounceTime`

  * *Type*: `integer`

 * *Default*: `250`
 
 \[DEPRECATED\] Specifies the debounce time limit\. Lower to increase responsiveness at the cost of possibile stability issues\.

### `kotlin.debugAdapter.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 \[Recommended\] Specifies whether the debug adapter should be used\. When enabled a debugger for Kotlin will be available\.

### `kotlin.debugAdapter.path`

  * *Type*: `string`

 * *Default*: `""`
 
 Optionally a custom path to the debug adapter executable\.

### `kotlin.externalSources.autoConvertToKotlin`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Specifies whether decompiled\/external classes should be auto\-converted to Kotlin\.

### `kotlin.externalSources.useKlsScheme`

  * *Type*: `boolean`

 * *Default*: `true`
 
 \[Recommended\] Specifies whether URIs inside JARs should be represented using the \'kls\'\-scheme\.

### `kotlin.indexing.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Whether global symbols in the project should be indexed automatically in the background\. This enables e\.g\. code completion for unimported classes and functions\.

### `kotlin.languageServer.debugAttach.autoSuspend`

  * *Type*: `boolean`

 \[DEBUG\] If enabled \(together with debugAttach\.enabled\)\, the language server will not immediately launch but instead listen on the specified attach port and wait for a debugger\. This is ONLY useful if you need to debug the language server ITSELF\.

### `kotlin.languageServer.debugAttach.enabled`

  * *Type*: `boolean`

 \[DEBUG\] Whether the language server should listen for debuggers\, i\.e\. be debuggable while running in VSCode\. This is ONLY useful if you need to debug the language server ITSELF\.

### `kotlin.languageServer.debugAttach.port`

  * *Type*: `integer`

 * *Default*: `5005`
 
 \[DEBUG\] If transport is stdio this enables you to attach to the running langugage server with a debugger\. This is ONLY useful if you need to debug the language server ITSELF\.

### `kotlin.languageServer.enabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 \[Recommended\] Specifies whether the language server should be used\. When enabled the extension will provide code completions and linting\, otherwise just syntax highlighting\. Might require a reload to apply\.

### `kotlin.languageServer.path`

  * *Type*: `string`

 * *Default*: `""`
 
 Optionally a custom path to the language server executable\.

### `kotlin.languageServer.port`

  * *Type*: `integer`

 * *Default*: `0`
 
 The port to which the client will attempt to connect to\. A random port is used if zero\. Only used if the transport layer is TCP\.

### `kotlin.languageServer.transport`

  `enum { "stdio", "tcp" }`

 * *Default*: `"stdio"`
 
 The transport layer beneath the language server protocol\. Note that the extension will launch the server even if a TCP socket is used\.

### `kotlin.linting.debounceTime`

  * *Type*: `integer`

 * *Default*: `250`
 
 \[DEBUG\] Specifies the debounce time limit\. Lower to increase responsiveness at the cost of possibile stability issues\.

### `kotlin.snippetsEnabled`

  * *Type*: `boolean`

 * *Default*: `true`
 
 \[DEPRECATED\] Specifies whether code completion should provide snippets \(true\) or plain\-text items \(false\)\.

### `kotlin.trace.server`

  `enum { "off", "messages", "verbose" }`

 * *Default*: `"off"`
 
 Traces the communication between VSCode and the Kotlin language server\.



