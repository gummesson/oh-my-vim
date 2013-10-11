# Oh my Vim!

A list of handy and interesting commands, keystrokes, settings and general tips for [(g)Vim](http://www.vim.org/).

## Commands

### `help 42`

`:help 42` makes you laugh.

### `help index`

`:help index` displays a list of all of the default commands in each mode.

### `lcd`

`:lcd` sets the current working directory for the current window only.

### `mksession`

`:mksession` saves the state of your current session which you can later restore by running `:source Session.vim` from command-line mode. You can give your session another name by using `:mksession {filename}`.

### `retab`

`:retab` replaces all sequences of white-space containing a `<Tab>` with new strings of whitespace using the given tabstop value.

### `shell`

`:shell` launches a shell console outside of Vim.

### `sort`

`:sort` sorts all selected lines.

### `TOHtml`

`:TOhtml` converts the current buffer into an HTML file with built-in syntax highlighting.

### `verbose map`

`:verbose map` displays a list of all of the mappings from the normal, visual and operator-pending mode.

`:verbose map!` displays a list of all the mappings from the replace, insert and command-line mode.

## Keystrokes

### `gd`

Press `gd` to go to a variable's declaration.

### `gi`

Press `gi` to get back to the last location in insert mode.

### `gqip`

Press `gqip` to reformat a paragraph around the `textwidth` setting.

### `gv`

Press `gv` to reselect the previous selection.

### `SHIFT-K`

Press `SHIFT-K` to lookup the keyword under the cursor.

## Settings

### `autochdir`

`set autochdir` sets the working directory to the current file.

### `autoread`

`set autoread` makes Vim re-read a file that has been changed outside of it.

### `cmdheight`

`set cmdheight={number}` sets the number of screen lines for the command-line.

### `copyindent`

`set copyindent` copies the structure of the existing lines indent when autoindenting a new line.

### `cursorcolumn`

`set cursorcolumn` highlights the screen column of the cursor.

### `errorformat`

`set errorformat={format}` specifies a list of formats for error messages that are recognized. The first format that matches with an error message is used.

### `fileformat`

`set fileformat={unix|mac|dos}` sets the current buffer's fileformat.

### `gdefault`

`set gdefault` makes the `s%` flag global by default. Use `/g` to turn the global option off.

### `language messages`

`language messages C` on Unix or `language messages en` on Windows sets the default interface language to english.

### `lazyredraw`

`set lazyredraw` makes the screen not redraw itself while executing macros, registers and other commands that have not been typed.

### `linespace`

`set linespace={number}` sets the number of pixel lines inserted between characters.

### `matchtime`

`set matchtime={number}` sets the tenths of a second to show the matching paren.

### `mousehide`

`set mousehide` hides the mouse pointer when characters are typed.

### `mousemodel`

`set mousemodel={extend|popup|popup_setpos}` sets the model to use for the mouse.

### `nojoinspaces`

`set nojoinspaces` makes Vim only insert one space when joining lines.

### `nrformats`

`set nrformats={octal|hex|alpha}` defines what bases Vim will consider for numbers when using the `CTRL-A` and `CTRL-X` commands for adding to and subtracting from a number respectively

### `numberwidth`

`set numberwidth={number}` sets the minimal number of columns to use for the line number.

### `rulerformat`

`set rulerformat` determines the content of the ruler.

### `scrollbind`

`set scrollbind` makes the current window scroll with other scrollbound windows.

### `shiftround`

`set shiftround` rounds the indent level to the multiple of `shiftwidth`.

### `showtabline`

`set showtabline={number}` specifies when the line with tab page labels will be displayed.

### `suffixes`

`set suffixes+={filetype}` sets the priority between files with almost the same name but different filetypes.

### `switchbuf`

`switchbuf={options}` controls the behavior when switching between buffers.

### `timeoutlen`

`set timeoutlen={milliseconds}` sets the time in milliseconds that is waited for a key code or mapped key sequence to complete.

### `wildignore`

`set wildignore+={filetype|folder}` sets a file/folder pattern that will get ignored by Vim.

## Tips

### Automatically wrap left and right

`set whichwrap+=<,>,h,l,[,]` will make the cursor move to the previous/next line after reaching the first/last character in the line.

### Count the occurrence of a pattern

`:%s/pattern//gn` will return a count of the occurrence of a specific pattern.

### Equal and unequal windows

- `set equalalways` makes all the windows automatically the same size after splitting or closing a window.
- `set noequalalways` reduces the size of the current window and leaves the other windows the same when splitting a window.  When closing a window the extra lines are given to the window next to it.`

### Go to first the first character on the next/previous line

- `+` goes downward.
- `-` goes upward.

### Increment and decrement a number

- `CTRL-A` increments a number that’s placed under the cursor.
- `CTRL-X` decrements it.

### Open multiple files in separate tabs

    :args path/to/files/*.*
    :tab all

### Persistent undo

- `set undofile` will automatically save your undo history when you write a file and restore the undo history when you edit the file again.
- `set undodir={path/to/dir}` will set the directory of the undofile.

### Remove cursorline when entering insert mode

    au InsertEnter * set nocursorline 
    au InsertLeave * set cursorline

### Remove sound and visual error

    set noerrorbells visualbell t_vb=
    au GUIEnter * set visualbell t_vb=

### Replace across multiple files

    :args path/to/files/*.*
    :argdo :%s/foo/bar/ge | update

### Stop the cursor from blinking

`set guicursor=a:blinkon0` stops the cursor from blinking.

### Uppercase and downcase

- `gUiw` makes the current word switch to uppercase.
- `guiw` makes the current word switch to lowercase.
- `gU$` switches to uppercase until end of line.
- `gu$` switches to lowercase until end of line.
