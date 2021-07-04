# GDScript (gdscript)

https://github.com/godotengine/godot

Language server for GDScript, used by Godot Engine.


## Setup

```lua
require'lspconfig'.gdscript.setup{}
```


### Default values

```lua
cmd = { "nc", "localhost", "6008" }
filetypes = { "gd", "gdscript", "gdscript3" }
root_dir = util.root_pattern("project.godot", ".git")
```




