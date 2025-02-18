### xplr.util.dirname

Get the directory name of a given path.

Type: function( path:string ) -> path:string|nil

Example:

```lua
xplr.util.dirname("/foo/bar")
-- "/foo"
```

### xplr.util.basename

Get the base name of a given path.

Type: function( path:string ) -> path:string|nil

Example:

```lua
xplr.util.basename("/foo/bar")
-- "bar"
```

### xplr.util.absolute

Get the absolute path of the given path by prepending $PWD.
It doesn't check if the path exists.

Type: function( path:string ) -> path:string

Example:

```lua
xplr.util.absolute("foo/bar")
-- "/tmp/foo/bar"
```

### xplr.util.explore

Explore directories with the given explorer config.

Type: function( path:string, config:[Explorer Config][1]|nil )
-> { node:[Node][2]... }

Example:

```lua

xplr.util.explore("/tmp")
xplr.util.explore("/tmp", app.explorer_config)
-- { { absolute_path = "/tmp/a", ... }, ... }
```

[1]: https://xplr.dev/en/lua-function-calls#explorer-config
[2]: https://xplr.dev/en/lua-function-calls#node

### xplr.util.shell_execute

Execute shell commands safely.

Type: function( program:string, args:{ arg:string... }|nil )
-> { stdout = string, stderr = string, returncode = number|nil }

Example:

```lua
xplr.util.shell_execute("pwd"})
xplr.util.shell_execute("bash", {"-c", "xplr --help"})
-- { stdout = "xplr...", stderr = "", returncode = 0 }
```

### xplr.util.shell_quote

Quote commands and paths safely.

Type: function( string ) -> string

Example:

```lua
xplr.util.shell_quote("a'b\"c")
-- 'a'"'"'b"c'
```
