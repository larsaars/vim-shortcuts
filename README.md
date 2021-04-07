# vim shortcuts / cheat sheet
> Note: This table is presupposes that you are using [my vim setup](https://github.com/larsaars/linux-setup).
## command mode
Every command can be executed n times by pressing a number and then entering the command.
All commands with a movement following (e.g. `c+movement`) can have a number before the movement (e.g. `c4l`).
#### movement
shortcut | behaviour | comment | example
--- | --- | --- | ---
h | move left
j | move down
k | move up
l | move right
w | move one word right (including next space)
W | same as `w`, but with punctuation jump
e | move one word right (excluding next space)
E | same as `e`, but with punctuation jump
b | move one word left
B | same as `b`, but with punctuation jump
$ | move to end of the line
0 | move to start of the line
^ | move to the first word of line | same as `0w`
% | move between two together belonging brackets
( | move code block up (at line position of first word)
) | move code block down (at line position of first word)
{ | move code block up (at line position zero)
} | move code block down (at line position zero)
f | jump to next occurrence of next entered character in line
F | jump to previous occurrence of next entered character in line
t | jump to next occurrence of next entered character in line - 1
T | jump to previous occurrence of next entered character in line - 1
; | repeat previous f, t, F or T movement 
, | repeat previous f, t, F or T movement, backwards
gg | move to top of file
G | move to bottom of file
number+gg | go to line number
gd | go to local declaration of variable
gD | go to global declaration of variable
g_ | jump to the last non-blank character of the line
ctrl+f | one page forward
ctrl+b | one page backwards
ctrl+d | move forward one half screen
ctrl+u | move backwards one half screen
zz | center cursor
ctrl+e | move screen down one line (without moving cursor)
ctrl+y | move screen up one line (without moving cursor)
enter or + | move down at line position of first word
/ | search regex-pattern | leave with `enter`
\# | search word at current cursor position and jump to next occurrence of it above
\* | search word at current cursor position and jump to next occurrence of it below
N | just jump in case of search to occurrence above
n | just jump in case of search to occurrence below
M | put cursor in middle of current screen
H | jump to top of the currently visible screen
L | jump to bottom of the currently visible screen
m+mark-name | set mark at current cursor position | marks with same name will be replaced | `ma`: mark with name a set at current cursor position
'+mark-name | jump to previously set mark | | when mark `a` has been set, jump with this to the previous cursor position

#### text manipulation
shortcut | behaviour | comment | example
--- | --- | --- | ---
u | undo
ctrl+r | redo
U | switch undo of whole line
r | replace character at current cursor position with next key press
R | switch to replace-mode, will replace all characters till exited
x | delete character at current cursor position
~ | switch case (upper or lower) of character at current cursor position and move one right
p | paste | stands for 'put'
y+movement | copy with the movement | stands for 'yank' | `y$` will copy till end of line
Y | copy to end of line | same as `y$`
d+movement | delete with the movement | | `d$` will delete till end of line
D | delete to end of line | same as `d$`
dd | delete line | actually cut it
yy | copy line
J | delete newline character in line below
<< | move line one tab left
\>> | move line one tab right
=G | indent file below cursor | in c, cpp, etc. with clang-format
!! | enter shell command, the result of it will be pasted below the cursor
ö | enter semicolon at end of the line
xp | swap two characters | cut then paste


#### switch to insert mode
shortcut | behaviour | comment | example
--- | --- | --- | ---
i | enter insert mode at cursor
I | enter insert mode at first word of line | same as `^i` or `0wi`
a | enter insert mode at cursor position + 1
A | enter insert mode at end of line
o | insert newline below and enter insert mode there (auto indented)
O | insert newline above and enter insert mode there (auto indented)
c+movement | delete to movement, move cursor there and enter insert mode
C | change till end of line | same as `c$`
cc | delete whole line and jump in insert mode
ä | enter curly-braces and move to insert mode between them

### insert mode
shortcut | behaviour | comment | example
--- | --- | --- | ---
esc | return to command mode
jk or kj | same as escape
ctrl+c | same as escape
ctrl+n | insert (auto-complete) next match before the cursor
ctrl+p | insert (auto-complete) previous match before the cursor
ctrl+t | move line one tab to right (indent)
ctrl+d | move line one tab to left (de-indent)
any key | use keyboard as you are used to | This setup auto-completes all types of brackets and quotation marks.

#### other
shortcut | behaviour | comment | example
--- | --- | --- | ---
. | repeat last action
K | open man page of cmd
" | toggle netrw
F2 | toggle paste mode | Paste with right mouse click and remember to leave this mode again (toggle back)!
F3 | `git pull`
F4 | `git add -A && git commit -m "...`
F5 | `git push`
F6 | beautify code | with clang-format, note that the [.clang-format file](https://github.com/larsaars/linux-setup/blob/main/.clang-format) is needed in the same dir as the code is
F7 | compile and execute code | [this](https://github.com/larsaars/linux-setup/blob/main/executevim.cpp) is used
F8 | toggle style | [codedark](https://github.com/tomasiser/vim-code-dark) (w/ modified bg) and [PaperColor](https://github.com/NLKNguyen/papercolor-theme)
F9 | toggle netrw | same as '"'
F10 | `:q!`
ZZ | `:q`

#### enter visual mode
shortcut | behaviour | comment | example
--- | --- | --- | ---
v | enter character visual mode | select single character
V | enter line visual mode | select whole lines
ctrl+v | enter block visual mode | select code blocks

### visual mode
In the visual mode, everything selected is affected by these commands. The visual mode gets exited after executing one command.

shortcut | behaviour | comment | example
--- | --- | --- | ---
v | select more or quit
d or x | delete | actually cut
y | copy | 'yank'
~ | swap case (upper and lower)
\> | shift one tab right
< | shift one tab left
movement | of any kind moves selection

### window manager
Press `ctrl+w` and then enter the next commands (from this table) for window mode and expected behaviour.

shortcut | behaviour | comment | example
--- | --- | --- | ---
w | switch between two windows
h | move to window on the left
j | move to window below
k | move to window above
l | move to window on right
v | create vertical split at right
n | create horizontal split
= | make viewports equal size
\- | decrease current viewport one line
\+ | increase current viewport one line
q | quit current window
r | rotate windows to right
R | rotate window to left


### tabs
shortcut | behaviour | comment | example
--- | --- | --- | ---
alt+j or gT | move to tab on the left
alt+k or gt | move to the tab on the right
\#gt number | go to specific tab number

### netrw (file manager)
> Note: Netrw is just a window, so controllable by window manager.
> Note: All vim commands are active here (concludes that searching with `/` for example is also possible).
> Note: Move between files with movement keys.

shortcut | behaviour | comment | example
--- | --- | --- | ---
F9 or " | toggle netrw
enter | if on folder, open it; if on file, replace current file in current window
v | open in vertical split | on file
t | open in new tab | on file

## commands
shortcut | behaviour | comment | example
--- | --- | --- | ---
:help keyword | shows help to vim command
:w | write
:q | quit
:q! | quit override
:wq | write quit
:wa | write all tabs
:wqa | write quit all tabs
:w filename | saves in with new filename | does not delete old file
:e | reload file
:e filename | edit a file
:r + filename | read file and paste it below cursor
:s | substitute
:set ic | enable ignore-case for search
:set noic | disable ignore-case for search
:delmarks mark-name | delete marks | | `delmarks abcd` or `delmarks a-d` deletes marks a, b, c and d
:bd | delete current buffer
:bn | switch to next buffer
:bp | switch to previous buffer
:sp filename | opens a new file and splits your screen horizontally to show more than one buffer
:vsp filename | opens a new file and splits your screen vertically to show more than one buffer
:ls | list all open buffers
:tabedit filename | open file in new tab
:tabclose | close a single tab
:tabs | list all open tabs

#### substitute command
> More info [here](https://vim.fandom.com/wiki/Search_and_replace).

shortcut | behaviour | comment | example
--- | --- | --- | ---
:s/foo/bar/g | replace 'foo' with 'bar' in current line
:%s/foo/bar/g | replace 'foo' with 'bar' in all lines
:%s/foo/bar/gc | change each 'foo' to 'bar', but ask for confirmation first
:5,12s/foo/bar/g | change each 'foo' to 'bar' for all lines from line 5 to line 12 (inclusive)
