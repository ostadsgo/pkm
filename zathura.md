Zathura saves selected text in `*` register which is the correct way to store selected text in X system.
applications like chrome don't make diff between `*` register and `+` register and store saved text in both registers.
Make Zathura to pupolate `+` and `*` register 
In `~/.config/zathura/zathurarc`
```bash
set selection-clipboard clipboard
set selection-clipboard primary
```
I didn't test this I use default setup of Zathura.

