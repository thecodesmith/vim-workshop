# Vim Intro


## Modes

Vim is a modal text editor. Learn each mode and take advantage of it.

* Normal or Command mode
* Insert mode
* Visual mode

i      Enter insert mode
v      Enter visual mode
<Esc>  Enter command mode


## Use `<NOP>` mappings to break bad habits

    noremap <key> <NOP>


## Movement

Don't use the cursor keys! Break the habit:

    noremap <Up> <NOP>
    noremap <Down> <NOP>
    noremap <Left> <NOP>
    noremap <Right> <NOP>


### Simple movement

h
j
k
l

Holding down j is a Vim anti-pattern.
Break that habit too. Use word-wise motions instead.

### Word-wise

w, W
b, B
e, E
0
$
I
A
%
]}
[{

### File-wise

gg
G
}
{

### Screen-wise

H
M
L

zb
zt
zz

### Using [count]

Apply it to (almost) any command.
Examples: 10j, 5fe


## Editing

i for Insert Mode

d
c
x
y
p
r
.

dd
yy

o, O


## Visual Block

v


## Text Objects

Learn these!

i[obj]
a[obj]

Objects:

w  word
p  paragraph
'  single-quoted string
"  quoted string
`  backtick
<  angle brackets
(
{
[

Examples:

iw
i(
i{


## Undo and Redo

u  undo
<ctrl-r>  redo


## Search and Replace

f, F  find
t, T  'til
Use with [count]

*  search word under cursor
/  search
?  search up
n  move to next match
N  move to previous match

:%s/old/new/gc  find/replace


## External Commands


:!command


## Completion

Ctrl-p in Insert Mode


## Marks

Set marks to quickly jump between locations in a document or between documents

Set mark:
m{a-zA-Z}

Jump to mark:
'{char}  first non-blank character on marked line
`{char}  exact position where mark was set

View marks:
:marks


## Tabs, Buffers, Windows

Don't use tabs. Use buffers instead.

:e file    edit file
:sp, :vsp  open in split
:buffers   view buffers
:b{N}      switch to buffer N
:sp N

:w   write file to disk
:q   quit
:q!  quit, discarding changes
:qa  quit all buffers
:wq  write and quit

Ctrl-W {h, j, k, l}  move between windows


## Macros

Replay single commands using `.`. For more than one command, use macros.

q{0-9a-zA-Z}  start recording a macro to specified macro buffer
qq  simplest way to record a macro
@q  replay macro in that macro buffer
@@  replay last played macro


## Vimrc and Plugins

https://github.com/thecodesmith/dotfiles/blob/master/vim/vimrc.symlink
Vundle plugin manager

### Some useful plugins

Ctrl-P
Tabularize
Commentary
Surround
NerdTree
Rooter
Tmux Navigator

Language support plugins:
groovy
yaml
go
