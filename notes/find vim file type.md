```lua
print(vim.bo.filetype)
```

```lua
local filetype = vim.bo.filetype
if filetype == "python" 
	vim.cmd("!ruff format")
elseif filetype == "lua"
	vim.cmd("...")
else
	vim.cmd("Unspported format for" .. filetype)
end
```