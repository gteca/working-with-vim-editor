## VIM Notes

VI is the linux text editor and VIM is VI IMproved.

VIM has three modes:
## Normal or Command mode
The mode that allows to execute VIM commands or operation on the text. \
To execute commands first we should type ```:[vim_command]``` \
**Examples**:

```:set number``` - Activate line numbers
```:w``` - Write changes to the file \
```:q``` - Quit the editor \
```:q!``` - Quit the editor and discard the changes made \
```:wq```  - Write changes to the file and quit the editor 

Changes made in the editor using the set command are not persistent. That means they will disappear when the editor is closed.
To make changes persistent we can edit the ```vimrc``` file.

Open the file using the command ```vim ~/.vimrc```
and the paste the configuration below. 
```
set number
syntax on
set tabstop=4
set shiftwidth=4
set autoindent
set mouse=a
colorscheme slate
```

Instead of using arrowkeys, we can navigate through the file using the keyboard letters:


<kbd>h</kbd> Move the cursor to the right \
<kbd>j</kbd> Move the cursor down \
<kbd>k</kbd> Move the cursor up \
<kbd>l</kbd> Move the cursor to theleft

- **Keybinding**
  - <kbd>u</kbd> - Undo changes (After edit the file and perhaps you want to undo the changes, switch to normal mode and undo)
  - <kbd>ctrl + r</kbd> - Redo
  - <kbd>cc</kbd> - Removes the content of the line and enters in the insert mode
  - <kbd>D</kbd> - Remove everything after the cursor
  - <kbd>dd</kbd> - deletes the whole line
  - <kbd>w</kbd> or <kbd>W</kbd> - jump to the next word (Something separated by space)
  - <kbd>b</kbd> - jump to the previous word (backwords)
  - <kbd>0</kbd> - sends the cursor to the begining of the line 
  - <kbd>$</kbd> - sends the cursor to the end of the line
  - <kbd>d0</kbd> - Delete from the cursor to the beginning of the line
  - <kbd>d$</kbd> - Delete from the cursor to the end of the line
  - <kbd>ci""</kbd> - Find the nearest quote signal, remove the content inside quote "" and start the insert mode between the empty quote. Very useful when we intend to remove a text and replace for a new one.
  - <kbd>ci(</kbd> - Find the nearest openning paranthesis, remove the content and enters the insert mode to start write inside the paranthesis. Very useful to remove the arguments of function and start writing new ones
  - <kbd>Line#G</kbd> - Go to Line#
  - <kbd>dw</kbd> - delete the next word 
  - <kbd>db</kbd> - delete the previous word
  - <kbd>diw</kbd> - delete in the middle of the word (delete the current work when the cursor is in the middle of it)
  - <kbd>%</kbd> - takes the cursor to the pairing closing parenthesis, curly brackets etc.
  - <kbd>==</kbd> - indent a line
  - <kbd>gg</kbd> - Go to the begin of the file 
  - <kbd>G</kbd> - Go to the end of the file 
  - <kbd>gg=G</kbd> - Indent the entire file

**We can combine numbers and keybinding, that multiplies the action
ex: 5k takes 5 lines up, 5h goes 5 characters right, 2u undo 2 times**

## Insert mode 
In the insert mode, whatever is written has no functionality and is just a text!. That means that any keyboard that we press when in the insert mode, is written in the file. There are many ways to enter in the insert mode:

<kbd>i</kbd> - Start the insert mode where the cursor is \
<kbd>I</kbd> - Start in the insert mode placing the cursor at the begining of the line \
<kbd>a</kbd> - Start the insert mode, one character after the cursor current position(append) \
<kbd>A</kbd> - Start the insert mode placing the cursor at the end of the line \
<kbd>o</kbd> - Start the insert mode opening a newline below the current line (open new line) \
<kbd>O</kbd> - Enter in the insert mode placing the cursor above the current line 

To leave the insert mode to the normal mode press ```esc```.

## Visual mode (For selecting)
The visual mode is for text selection. There are three visual modes, but here I mention only two:
- <kbd>v</kbd> - Start visual mode, and allows to select character by character
- <kbd>V</kbd> - Visual mode that allows to select line by line

- **Keybinding**

<kbd>d</kbd> - Deletes the selected (highlighted) text (You always can undo the deletion using ```u``` when swtching to normal mode \
<kbd>y</kbd> - copy a text to the clipboard \
<kbd>yy</kbd> or </kbd>Y</kbd> - Copy the entire line \
<kbd>p</kbd> - paste a text to the editor below the current line \
<kbd>P</kbd> - Paste the text to the editor above the current line \
<kbd>c</kbd> - remove the highlighted text and enter in teh insert mode (change) \
<kbd>r</kbd> - replace a character

## Searching

 - ```/myword``` - search for ```myword``` inside the next
- <kbd>n</kbd> - next occurence
- <kbd>N</kbd> - previous occurrence
- ```:%s/character/symbol/g``` - Replace the word character by symbol (global).
To remove only a particular thing just select the text.


# waypoint 
<kbd>ma</kbd> - Mark this line a point to return if we want to go back just <kbd>'a</kbd>.
The character <kbd>a</kbd> is arbitrary, one can specify any character from the alphabet, or have multiples waypoints.
