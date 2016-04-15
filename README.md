# lua-shell
run shell with escaped arguments from Lua

````Lua
shell = require("shell")

-- run `ls -la .` using popen with escaped args
h = io.popen(shell.escape{"ls", "-la", "."})
output = h:read("*a"))
retcode = h:close()

-- run `ls -la .`, same as above
retcode, output = shell.run{"ls", "-la", "."}

-- run `ls -la .` using os.execute with escaped args
shell.execute{"ls", "-la", "."}

````

