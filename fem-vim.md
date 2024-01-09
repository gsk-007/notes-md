- ```:h usr<tab> ``` for help in vim

# The Terminology

### Buffer
```:h buffer ```  A buffer contains the text of the file and is what you edit

### Window
```:h window ``` A window displays a buffer

### Tabs
```:h tab``` A tab is another viewport

### Splits 
```:h split``` A split refers to splitting the viewport in n splits

### Help Menu
```:h<enter>``` To access the help menu

### Motion
A motion is a command that moves the cursor.
```:h motion```  for refering the docs

### Abbreviations
Ctrl+a ->`<C-a>`
Enter -> `<CR>`
Tab -> `<tab>`
Escape -> `<esc>`
space -> `<space>`


# Modes

- Normal (vim opens in normal mode)
- Insert (to write)
- Visual
- Visual Line

> type `:q` to quit vim

## Basic Motions
-   h(left), j(down), k(up), l(right) for basic movement.
-   w,b for word hopping. Effectively the same as Option/Ctrl + arrow keys
-   yy to "copy" a line, called Yank
-   dd to delete, and yank, a line
-   x to delete a character on the cursor
-   p and P to paste the contents of the implicit register below / above
-   Most of the ways to go into insert mode!
    - i and a for  side of the cursor
    -  I and A for  side of the line
    -  o and O for below / above line
-   zz - I snuck that one in... (recenter the screen)
-  u to undo
-  Shift+D to delete everything from cursor to end of line

> Use numbers before commands to repeat them n times

#### Visual Mode
Highlight part of this line by pressing v, then navigate around 
escape to leave visual mode
- Visual Mode + y / p (yank and paste)

#### Visual Line Mode
Highlight this line by pressing V, then navigate around
escape to leave visual mode
- Visual Mode + d / p (delete and paste)

##### The relationship of y / d
:h reg
:reg
- Yank will be preserved for 1 register
- delete will be preserved (in order of history) for rest 9 registers

### How do you know what is available?
-   You can google. Sometimes that is a good thing.
-   `h options`
-   `h <tabcomplete or ctrl-d>`
-   `h <specific option name>`

- `:Ex` to open explore view in current directory

### Split the window
- `:Vex` vertical split
- `:Sex` horizontal split
- `Ctrl+w+v` shortcut for vertical split
- `Ctrl+w+s` shortcut for horizontal split
- `Ctrl+w+o` closes everything but current buffer


### Files and Navigation
#### Edit
`:e <ctrl-d>/<tab>` ctrl d for files and tab for auto completion
- Telescope.nvim plugin

### Marks
- To mark a file press `m` the choose a letter (preffered **uppercase** for **global**(the project directory) and **lowercase** for **file level**(current file/buffer))
- to navigate between marks press `'<MarkLetter>`.(single quotes followed by letter) Ex: If i chose `G` for `sockets.c`, and to navigate there I simply press `'G`

### Alternate Files
- `"%` holds current file
- `"#` holds previous file
-  Use `ctrl+^` to jump back and forth between the files

### Jumplist
`:h jumplist` to read about jumplists
- `Ctrl+o` to go backwards in jumplist
- `Ctrl+i` to go forward in jumplist

### Navigation in Fzf
- `Ctrl+p / Ctrl+k` to go up
- `Ctrl+n / Ctrl+j` to go down

Ripgrep tool

## Quickfix
- Add items to quick fix list
- When dealing with a quickfix you need 3 commands primarily, `:copen`, `:cnext`, and `:cprev`. Lets try `:copen` first
- In vimrc/init.nvim
```viml
I don't know if I love these remaps yet.  I am considering doing
" <leader>c(k|j|o)
nnoremap <C-k> :cnext<CR>
nnoremap <C-j> :cprev<CR>
nnoremap <C-E> :copen<CR>
```


## Search And Replace

### Basic Search
- using `/` as  `/<word><CR>`
- `n` to jump to next one `N` to go backwards
- We can use regex for searching

To Search in a selected region
- Highlight the portion in visual mode
- press `:`
-  `s/<word to search>/<word to replace>`
- For full file `%s/<word to search>/<word to replace>/{g-Global,c-options}`

## Macros
- press `q`  it puts you into macro mode
- press `a` to start recording (or any other preffered letter)
- record your macro
- press `q` again to quit recording
- use `@a` to use the macro

> Ctrl+ a will increment any number it sees in the line

## Advance Motions

### Change
`c` is a powerful motion.  You use it just like `d` but at the end of the
motion you are ejected from `NORMAL` and into `INSERT`.
So if you wished to delete a word and then type in a new word, `c` is a great
habit to form.


### Horizontal Movement

-  `_`   go to the first non whitespace character
-  `0`   go to the beginning of the line
-  `$`    go to the end of the line
-  `D`    delete
-  `C`    delete 
-  `S`    delete the whole line and go into insert mode
-  `s`    delete a character and go into insert mode
-  `f`     jump to the first occurence of a character
-  `,`    goes forward in the list
-  `;`    goes backward in the list
-  `t`    jump upto the first occurence of a character
-  `F`    same as f but backwards
-  `T`    same as t but backwards

### Vertical Movements
- `{` and `}`  jump by paragraph(continuous block of code)
- `Ctrl+d/u`  d jump down half page, u jump up by half page
- `[m` / `]m` and `[M` / `]M`     ]m next opening brace 
This will move by "function".  
- `%`  jump between bracket pairs

- `di{` delete inside { } 
- `da{`   delete inside with { }
- can use with v,c
- o to jump between visual selection
- `diw` to delete a word 
- `diW`  to delete a non white space content
- `dap/dip` delete by paragraphs









![[Pasted image 20230318141901.png]]
