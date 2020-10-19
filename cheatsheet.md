# Vim Cheatsheet
Work in progress

## Insert Mode
i - insert text before cursor
a - append text after cursor
o - starts new line below cursor & insert text
<esc> - exits insert mode

## Normal mode
. - replay previous change
u - undo
Ctrl-r - redo

## Visual mode:
v - character-wise
V - line-wise
Ctrl-v - block-wise

## Command-line mode:
:!command - execute an external command
:h - help

## Buffers:
:new - create new buffer
:ls - list all buffers
:buffer [n] - select buffer n
:bdelete [n] - delete buffer n

## Windows:
:split [filename] - horizontal slit
:vsplit [filename]- vertical split
Ctrl-w h - choose left window
Ctrl-w j - choose down window
Ctrl-w k - choose up window
Ctrl-w l - choose right window
Ctrl-w v - open vertical split
Ctrl-w s - open horizontal split
Ctrl-w c - close window
Ctrl-w o - make current window the only one on screen and closes other

## Tabs:
:tabnew [filename] - open new tab
:tabclose - close tab
gt - go to next tab
gT - go to previous tab

## Operators:
y - yank (copy)
d - delete and save to register
c - change
p - paste

## Text Objects:
w - word
s - sentence
p - paragraph
i - inner text object
a - text object + whitespace

## Motions:
h - left
j - down
k - up
l - right
0 - beginning of the line
$ - end of the line
w - beginning of the next word
e - end of the next word
b - beginning of the previous word
( - previous sentence
) - next sentence
{ - previous paragraph
} - next paragraph
% - another match of (), [], {}
nG - go to n line
gg - go to 1st line
G - go to last line

## Search:
/ - search forward
? - search backward
n - next search match
N - previous search match
* - search for whole word under cursor forward
# - search for whole word under cursor backward
g* - search for word under cursor forward
g# - search for word under cursor backward

## Substitution:
:s/old/new/ - substitute the first match
:s/old/new/g - substitute all matches

## Macros:
qa - start recording macro in register a
q - stop recording macro
@a - execute macro from register a
@@ - execute last executed macros

## Fold:
zf[operator] - fold according operator (motion or text object)
zo - open folded text
zc - close fold


## terminals
:vert term          " open term vertically. Try map to S-F4


## configs
filetype detect    " auto-detects file type
filetype plugin indent on
syntax on
set hidden		" allows to switch buffer without saving (preserving curr buff in the bg)

## auto-formatting
set shiftwidth=4 tabstop=4 softtabstop=4 expandtab autoindent smartindent
:retab " reapplies formatting to current file

## cmd line mode
^-F: edit previous commands

## finding files recursively with `find`
set path=.,**                           " where **=recursively
set wildignore=*.pyc                    " files you want to ignore

" then:
:find myfile.py

## runtimepath
a list of directories which will be searched for runtime files. Order:
1. user home .vim
2. sysadmin folder
3. $VIMRUNTIME
4. Sysadmin "after" folder
5. User home "after" folder

## ctags
:!ctags -R

ctags config ex:
```
--langdef=Go
langmap=Go:.Go
regex-Go=//todo:: continue
```

## building
configure a ~/.vim/compiler/go.vim file
:compile
:make
:copen - lists errors
:cp / :cp 
