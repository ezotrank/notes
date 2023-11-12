Nvim
==========

Insert Mode
-----------

```text
CTRL+h - Delete the character before the cursor.
CTRL+w - Delete the word under the cursor.
CTRL+u - Delete everything before the cursor.
CTRL+t - Add one indentation.
CTRL+d - Delete one indentation.
CTRL+x CTRL-l - Complete a whole line from the content of one of your buffer.
CTRL+x s - Complete with spelling suggestions
```

Normal Mode
-----------

```text
gf - Edit the file located at the filepath under your cursor.
     You can use CTRL+W CTRL+F to open the file in a new window.
gx - Open the file located at the filepath under your cursor.
gi - Move to the last insertion you did and switch to INSERT mode.
gv - Start VISUAL mode and use the selection made during the last VISUAL mode.
gn - Select the match of your last search.
gI - Insert text at the beginning of the line, no matter what the first
     characters are.
gu - Lowercase using a motion (for example, guiw).
gU - Uppercase using a motion (for example, gUiw).


ctrl + b to move a page screen back or "up"
ctrl + f to move a page screen front or "down"
ctrl + u to move a ½ page screen up
ctrl + d to move a ½ page screen down
ctrl + y to move the screen up one line
ctrl + e to move the screen down one line
z + z to move the current line I'm on to the center of the screen
z + t to move the current line I'm on to the top of the screen
z + b to move the current line I'm on to the bottom of the screen
```

goto:

```text
gr - Search references
```

marks:

```text
<leader>sm - Jump to Mark
m[a-zA-Z] - Set mark
'[a-zA-Z] - Jump to line of mark
d'[a-zA-Z] - Delete from current line to line of mark
]' - Jump to next line with a lowercase mark
[' - Jump to previous line with a lowercase mark
]` - Jump to next lowercase mark
[` - Jump to previous lowercase mark
:marks - List all the current marks
:marks aB - List marks a,B
:delmarks! - Delete all lowercase marks for the current buffer
:delmarks - aA Delete marks a,A
```

telescope:

```text
<leader>, Switch Buffer
<leader>: Command History
<leader>fb Buffers
<leader>fr Recent
<leader>fR Recent (cwd)
<leader>gc Commits
<leader>gs status
<leader>sb Buffer
<leader>sd Document diagnostics
<leader>sD Workspace diagnostics
<leader>sh Help Pages
<leader>sk Key Maps
<leader>sm Jump to Mark
<leader>sM Man Pages
<leader>sR Resume
<leader>ss Goto Symbol
<leader>sS Goto Symbol (Workspace)
```

Visual Mode
-----------

```text
p - replace the selected text with contents of the default " register
    See :h v_p for more details, corner cases, uppercase P command behavior, etc
c - clear the selected text and change to Insert mode.
C - similar to c but clears till end of lines before changing to Insert mode.
gq - wrap lines in a specific area
gqq - wraps the current line
gqip - wraps the current paragraph.
```

Spell
-----

```text
:set spell – Turn on spell checking
:set nospell – Turn off spell checking
]s – Jump to the next misspelled word
[s – Jump to the previous misspelled word
z= – Bring up the suggested replacements
zg – Good word: Add the word under the cursor to the dictionary
zw – Woops! Undo and remove the word from the dictionary
```

Registers
---------

```text
:reg - Display the content of your registers
"<reg> - This keystroke specifies the register <reg> to be read or written.
<leader>s" - List registers
```

Types of registers:

- The unnamed register (`"`) - Contain the last deleted, changed, or yanked
  content, even if one register was specified.
- The numbered registers (from `0` to `9`). The stack of deleted/changed. None of
  these registers are written if you've specified one before with the keystroke `"`.
- The small delete register (`-`). Contains any deleted or changed content
  smaller than one line.
- The named registers (range from `a` to `z`). You can use the uppercase name of
  each register to append to it (instead of overwriting it).
- The black hole register (`_`) - Everything written in there will disappear forever.
- The last search pattern register (`/`)

Help
----

```text
:help key-notation
:help i_CTRL-x
:help redir
:help verbose-cmd
```

Misc
----

```text
messages
gg dG - clear file content.
set textwidth=72
set colorcolumn=72
.!fmt -80 -s
J - joining multiple lines
Lge - Git Explorer
Lbe - Buffer Explorer
Lce - Code Explorer
```

To Sort Out
-----------

...

## See Also:

- [Vim Commands: A Beginner Guide with Examples](https://thevaluable.dev/vim-commands-beginner/)
- [Vim Reference Guide](https://learnbyexample.github.io/vim_reference/cover.html)
- [Using Marks](https://vim.fandom.com/wiki/Using_marks)
- [LazyVim Keymaps](https://www.lazyvim.org/keymaps#telescopenvim)
