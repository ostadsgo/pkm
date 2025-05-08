### Sessions

- **`Ctrl-b d`**: Detach from the current session.
- **`Ctrl-b s`**: List all sessions.
- **`Ctrl-b $`**: Rename the current session.
- **`Ctrl-b (`**: Switch to the previous session.
- **`Ctrl-b )`**: Switch to the next session.
    

### Windows

- **`Ctrl-b c`**: Create a new window.
- **`Ctrl-b &`**: Close the current window.
- **`Ctrl-b w`**: List all windows.
- **`Ctrl-b p`**: Switch to the previous window.
- **`Ctrl-b n`**: Switch to the next window.
- **`Ctrl-b ,`**: Rename the current window.
- **`Ctrl-b 0-9`**: Switch to window by number.
    

### Panes

- **`Ctrl-b %`**: Split the current pane vertically.
- **`Ctrl-b "`**: Split the current pane horizontally.
- **`Ctrl-b o`**: Switch to the next pane.
- **`Ctrl-b ;`**: Toggle between the current and previous pane.
- **`Ctrl-b x`**: Close the current pane.
- **`Ctrl-b z`**: Zoom in/out of the current pane.
- **`Ctrl-b {`**: Move the current pane to the left.
- **`Ctrl-b }`**: Move the current pane to the right.
- **`Ctrl-b Space`**: Toggle between pane layouts.
    

### Copy Mode

- **`Ctrl-b [`**: Enter copy mode.
- **`Ctrl-b ]`**: Paste content of tmux buffer
- **`Ctrl-b PgUp`**: Enter copy mode and scroll up.
- **In copy mode**:
    - **`q`**: Exit copy mode.
    - **`Ctrl-u`**: Scroll up half a page.
    - **`Ctrl-d`**: Scroll down half a page.
    - **`Ctrl-b`**: Scroll up one page.
    - **`Ctrl-f`**: Scroll down one page.
    - **`/`**: Search forward.
    - **`?`**: Search backward.
    - **`n`**: Repeat the last search.
    - **`N`**: Repeat the last search in reverse.
    - **`Enter`**: Copy the selected text and exit copy mode.
        

### Miscellaneous

- **`Ctrl-b t`**: Show the time.
- **`Ctrl-b ?`**: List all keybindings.
- **`Ctrl-b :`**: Enter command mode.
    

### Custom Keybindings

You can customize keybindings in your `~/.tmux.conf` file. For example:

```bash
# Change the prefix key to Ctrl-a
unbind C-b
set-option -g prefix C-a
bind-key C-a send-prefix

# Split panes using | and -
bind | split-window -h
bind - split-window -v
unbind '"'
unbind %

# Reload the config file
bind r source-file ~/.tmux.conf \; display "Reloaded!"
```
	
# Reload the config file
bind r source-file ~/.tmux.conf \; display "Reloaded!"
