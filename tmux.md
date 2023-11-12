# tmux

tags: #tmux #cli


**Sessions**

$ tmux new -s mysession

:new -s mysession

Ctrl + b $ - rename session

Ctrl + b d - detatach from session

tmux ls - list sessions

Ctrl + b s show all session

tmux a attach to the session

tmux a -t mysession attach to the session


**Windows**

Ctrl + b , - rename current window

Ctrl + b & - close current window

Ctrl + b w - list windows

Ctrl + b p - previous window

Ctrl + b n - next window

Ctrl + b l - toogle last active window


**Panes**

Ctrl + b ; - toggle last active pane

Ctrl + b % - split vertical

Ctrl + b " - split horizontal

Ctrl + b q - show pane numbers

Ctrl + b q 0 ... 9 switch/select pane by number

Ctrl + b o - switch to next pane

Ctrl + b Spacebar - toggle between pane layouts


**Copy**

Ctrl + b [ enter copy mode

Ctrl + b ] paste contents of buffer_0

Ctrl + b : enter command mode


Windows
-------

```
swap-window -t 0
swap-window -s 3 -t 1
```

## Links:

- [Tmux Cheat Sheet & Quick Reference](https://tmuxcheatsheet.com)
