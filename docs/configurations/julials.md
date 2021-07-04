# Julia (julials)

https://github.com/julia-vscode/julia-vscode

`LanguageServer.jl` can be installed with `julia` and `Pkg`:
```sh
julia -e 'using Pkg; Pkg.add("LanguageServer"); Pkg.add("SymbolServer")'
```
The default config lazily evaluates the location of the julia language server from the your global julia packages.
This adds a small overhead on first opening of a julia file. To avoid this overhead, replace server_path in on_new_config with
a hard-coded path to the server.

```lua
require'lspconfig'.julials.setup{
    on_new_config = function(new_config,new_root_dir)
      server_path = "/path/to/directory/containing/LanguageServer.jl/src"
      cmd = {
        "julia",
        "--project="..server_path,
        "--startup-file=no",
        "--history-file=no",
        "-e", [[
          using Pkg;
          Pkg.instantiate()
          using LanguageServer; using SymbolServer;
          depot_path = get(ENV, "JULIA_DEPOT_PATH", "")
          project_path = dirname(something(Base.current_project(pwd()), Base.load_path_expand(LOAD_PATH[2])))
          # Make sure that we only load packages from this environment specifically.
          @info "Running language server" env=Base.load_path()[1] pwd() project_path depot_path
          server = LanguageServer.LanguageServerInstance(stdin, stdout, project_path, depot_path);
          server.runlinter = true;
          run(server);
        \]\]
    };
      new_config.cmd = cmd
    end
}
```
You can find the path to the globally installed LanguageServer.jl package with the following command:

```bash
julia -e 'print(Base.find_package("LanguageServer"))'
```

Note: the directory passed to `--project=...` should terminate with src, not LanguageServer.jl.

    

## Setup

```lua
require'lspconfig'.julials.setup{}
```


### Default values

```lua
cmd = { "julia", "--startup-file=no", "--history-file=no", "-e", '    using Pkg;\n    Pkg.instantiate()\n    using LanguageServer; using SymbolServer;\n    depot_path = get(ENV, "JULIA_DEPOT_PATH", "")\n    project_path = dirname(something(Base.current_project(pwd()), Base.load_path_expand(LOAD_PATH[2])))\n    # Make sure that we only load packages from this environment specifically.\n    @info "Running language server" env=Base.load_path()[1] pwd() project_path depot_path\n    server = LanguageServer.LanguageServerInstance(stdin, stdout, project_path, depot_path);\n    server.runlinter = true;\n    run(server);\n  ' }
filetypes = { "julia" }
on_new_config = function(new_config, _)
      local server_path = vim.fn.system "julia --startup-file=no -q -e 'print(Base.find_package(\"LanguageServer\"))'"
      local new_cmd = vim.deepcopy(cmd)
      table.insert(new_cmd, 2, "--project=" .. server_path:sub(0, -19))
      new_config.cmd = new_cmd
    end,
root_dir = function(fname)
      return util.find_git_ancestor(fname) or vim.fn.getcwd()
    end,
```


This server accepts configuration via the `settings` key.

## Available settings

### `julia.NumThreads`

  * *Type*: `integer|null`

 * *Default*: `vim.NIL`
 
 Number of threads to use for Julia processes\.

### `julia.additionalArgs`

  * *Type*: `array`

 * *Default*: `{}`
 
 Additional Julia arguments\.

### `julia.completionmode`

  `enum { "exportedonly", "import", "qualify" }`

 * *Default*: `"import"`
 
 Sets the mode for completions\.

### `julia.debuggerDefaultCompiled`

  * *Type*: `array`

 * *Default*: `{ "Base.", "-Base.!", "-Base.all", "-Base.all!", "-Base.any", "-Base.any!", "-Base.cd", "-Base.iterate", "-Base.collect", "-Base.collect_similar", "-Base._collect", "-Base.collect_to!", "-Base.collect_to_with_first!", "-Base.filter", "-Base.filter!", "-Base.foreach", "-Base.findall", "-Base.findfirst", "-Base.findlast", "-Base.findnext", "-Base.findprev", "-Base.Generator", "-Base.map", "-Base.map!", "-Base.maximum!", "-Base.minimum!", "-Base.mktemp", "-Base.mktempdir", "-Base.open", "-Base.prod!", "-Base.redirect_stderr", "-Base.redirect_stdin", "-Base.redirect_stdout", "-Base.reenable_sigint", "-Base.setindex!", "-Base.setprecision", "-Base.setrounding", "-Base.show", "-Base.sprint", "-Base.sum", "-Base.sum!", "-Base.task_local_storage", "-Base.timedwait", "-Base.withenv", "Core", "Core.Compiler.", "Core.IR", "Core.Intrinsics", "DelimitedFiles", "Distributed", "LinearAlgebra.", "Serialization", "Statistics", "-Statistics.mean", "SparseArrays", "Mmap" }`
 
 Functions or modules that are set to compiled mode when setting the defaults\.

### `julia.deleteJuliaCovFiles`

  * *Type*: `boolean`

 * *Default*: `"true"`
 
 Delete Julia \.cov files when running tests with coverage\, leaving only a \.lcov file behind\.

### `julia.editor`

  * *Type*: `string|null`

 * *Default*: `vim.NIL`
 
 null

### `julia.enableCrashReporter`

  * *Type*: `boolean|null`

 * *Default*: `vim.NIL`
 
 Enable crash reports to be sent to the julia VS Code extension developers\.

### `julia.enableTelemetry`

  * *Type*: `boolean|null`

 * *Default*: `vim.NIL`
 
 Enable usage data and errors to be sent to the julia VS Code extension developers\.

### `julia.environmentPath`

  * *Type*: `string|null`

 * *Default*: `vim.NIL`
 
 Path to a julia environment\. VS Code needs to be reloaded for changes to take effect\.

### `julia.executablePath`

  * *Type*: `string`

 * *Default*: `""`
 
 Points to the julia executable\.

### `julia.execution.codeInREPL`

  * *Type*: `boolean`

 Print executed code in REPL and append it to the REPL history\.

### `julia.execution.inlineResults.colors`

  * *Type*: `object`

 * *Default*: `vim.empty_dict()`
 
 null

### `julia.execution.resultType`

  `enum { "REPL", "inline", "inline, errors in REPL", "both" }`

 * *Default*: `"REPL"`
 
 Specifies how to show inline execution results

### `julia.focusPlotNavigator`

  * *Type*: `boolean`

 Whether to automatically show the plot navigator when plotting\.

### `julia.format.calls`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Format function calls\.

### `julia.format.comments`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Format comments\.

### `julia.format.curly`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Format braces\.

### `julia.format.docs`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Format inline documentation\.

### `julia.format.indent`

  * *Type*: `integer`

 * *Default*: `4`
 
 Indent size for formatting\.

### `julia.format.indents`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Format file indents\.

### `julia.format.iterOps`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Format loop iterators\.

### `julia.format.keywords`

  * *Type*: `bool`

 * *Default*: `true`
 
 Ensure single spacing following keywords\.

### `julia.format.kwarg`

  `enum { "none", "single", "off" }`

 * *Default*: `"none"`
 
 Format whitespace around function keyword arguments\.

### `julia.format.ops`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Format whitespace around operators\.

### `julia.format.tuples`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Format tuples\.

### `julia.lint.call`

  * *Type*: `boolean`

 * *Default*: `true`
 
 This compares  call signatures against all known methods for the called function\. Calls with too many or too few arguments\, or unknown keyword parameters are highlighted\.

### `julia.lint.constif`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Check for constant conditionals in if statements that result in branches never being reached\.\.

### `julia.lint.datadecl`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Check variables used in type declarations are datatypes\.

### `julia.lint.disabledDirs`

  * *Type*: `array`

 * *Default*: `{ "docs", "test" }`
 
 null

### `julia.lint.iter`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Check iterator syntax of loops\. Will identify\, for example\, attempts to iterate over single values\.

### `julia.lint.lazy`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Check for deterministic lazy boolean operators\.

### `julia.lint.missingrefs`

  `enum { "none", "symbols", "all" }`

 * *Default*: `"none"`
 
 Highlight unknown symbols\. The \`symbols\` option will not mark unknown fields\.

### `julia.lint.modname`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Check submodule names do not shadow their parent\'s name\.

### `julia.lint.nothingcomp`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Check for use of \`\=\=\` rather than \`\=\=\=\` when comparing against \`nothing\`\. 

### `julia.lint.pirates`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Check for type piracy \- the overloading of external functions with methods specified for external datatypes\. \'External\' here refers to imported code\.

### `julia.lint.run`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Run the linter on active files\.

### `julia.lint.typeparam`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Check parameters declared in \`where\` statements or datatype declarations are used\.

### `julia.lint.useoffuncargs`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Check that all declared arguments are used within the function body\.

### `julia.liveTestFile`

  * *Type*: `string`

 * *Default*: `"test/runtests.jl"`
 
 A workspace relative path to a Julia file that contains the tests that should be run for live testing\.

### `julia.packageServer`

  * *Type*: `string`

 * *Default*: `""`
 
 null

### `julia.persistentSession.enabled`

  * *Type*: `boolean`

 null

### `julia.persistentSession.shell`

  * *Type*: `string`

 * *Default*: `"/bin/sh"`
 
 Shell used to start the persistent session\.

### `julia.persistentSession.shellExecutionArgument`

  * *Type*: `string`

 * *Default*: `"-c"`
 
 null

### `julia.persistentSession.tmuxSessionName`

  * *Type*: `string`

 * *Default*: `"julia_vscode"`
 
 null

### `julia.trace.server`

  `enum { "off", "messages", "verbose" }`

 * *Default*: `"off"`
 
 Traces the communication between VS Code and the language server\.

### `julia.useCustomSysimage`

  * *Type*: `boolean`

 Use an existing custom sysimage when starting the REPL

### `julia.usePlotPane`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Display plots within VS Code\. Might require a restart of the Julia process\.

### `julia.useProgressFrontend`

  * *Type*: `boolean`

 * *Default*: `true`
 
 null

### `julia.useRevise`

  * *Type*: `boolean`

 * *Default*: `true`
 
 Load Revise\.jl on startup of the REPL\.



