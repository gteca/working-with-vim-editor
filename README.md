## VIM Notes

VIM means VI IMproved. VIM is a text editor for most UNIX systems and Apple OS X.

VIM has four modes:
## Command mode
The command mode allows to execute VIM commands. The commands are typed at the bottom of the editor and preceeded by ```:``` \.
- **Examples of VIM commands**:
  - ```:set number``` Activate line numbers in the text editor (By default vim does not display the line numbers)
  - ```:w``` Write the changes to the file 
  - ```:q``` Quit the editor 
  - ```:q!``` Quit the editor and discard all the changes made since the moment the file was opened
  - ```:wq``` Write changes to the file and quit the editor 

Changes made in the editor using the set command are not persistent. That means they will disappear when the editor is closed.
To make changes persistent we can edit the ```vimrc``` file.

Open the file using the command ```vim ~/.vimrc```
and the paste the configuration below. 
``` vim
set number
syntax on
set tabstop=4
set shiftwidth=4
set autoindent
set mouse=a
colorscheme slate
```

## Normal mode
The normal is the default mode. The normal mode allows navigating through the text (text means anything displayed in the editor including source code) and execute operations on the text

To navigate through the text, instead of using arrowkeys, we can also navigate through the text using the keyboard letters:


- <kbd>h</kbd> Move the cursor to the right 
- <kbd>j</kbd> Move the cursor down 
- <kbd>k</kbd> Move the cursor up 
- <kbd>l</kbd> Move the cursor to the left

- **Keybinding**
  - <kbd>u</kbd> Undo changes
  - <kbd>ctrl + r</kbd> Redo changes
  - <kbd>cc</kbd> Removes the content of the line and switch to the insert mode
  - <kbd>D</kbd> Remove everything after the cursor
  - <kbd>dd</kbd> Deletes the entire line
  - <kbd>w</kbd> or <kbd>W</kbd> - Jump to the next word in the text
  - <kbd>b</kbd> Jump to the previous word (backwords)
  - <kbd>0</kbd> Sends the cursor to the begining of the line 
  - <kbd>$</kbd> Sends the cursor to the end of the line
  - <kbd>d0</kbd> Delete from the cursor's current position to the beginning of the line
  - <kbd>d$</kbd> Delete from the cursor's current position to the end of the line
  - <kbd>ci"</kbd> Find the nearest quotation mark in the cursor's current line, remove the content inside quote ", switch to insert mode and place the cursor between the empty quote (very useful when we intend to remove a text and replace for a new one)
  - <kbd>ci(</kbd> Find the nearest openning paranthesis in the cursor's current line, remove the content, switch insert to insert mode and to place the cursor inside the paranthesis (very useful to remove the arguments of function and start writing new ones)
  - <kbd>numberG</kbd> Go to Line ```number```
  - <kbd>dw</kbd> Delete the next word (next word means the word after the word of cursor's current position) 
  - <kbd>db</kbd> Delete the previous word
  - <kbd>diw</kbd> Delete in the middle of the word (delete the current work when the cursor is in the middle of it)
  - <kbd>%</kbd> Takes the cursor to the pairing closing parenthesis, curly brackets etc.
  - <kbd>==</kbd> Indent a line
  - <kbd>gg</kbd> Go to the begin of the file 
  - <kbd>G</kbd> Go to the end of the file 
  - <kbd>gg=G</kbd> Indent the entire file

**We can combine numbers and keybinding, that multiplies the action
ex: 5k takes 5 lines up, 5h goes 5 characters right, 2u undo 2 times**

## Insert mode 
In the insert mode, whatever is written has no functionality and is just a text!. That means that any keyboard that we press when in the insert mode, is written in the file. There are many ways to enter in the insert mode:

- <kbd>i</kbd> Start the insert mode where the cursor is 
- <kbd>I</kbd> Start in the insert mode placing the cursor at the begining of the line 
- <kbd>a</kbd> Start the insert mode, one character after the cursor current position(append) 
- <kbd>A</kbd> Start the insert mode placing the cursor at the end of the line 
- <kbd>o</kbd> Start the insert mode opening a newline below the current line (open new line) 
- <kbd>O</kbd> Enter in the insert mode placing the cursor above the current line 

To leave the insert mode to the normal mode press <kbd>esc</kbd>.

## Visual mode (For selecting)
The visual mode is for text selection. There are three visual modes, but here I mention only two:
- <kbd>v</kbd> Start visual mode, and allows to select character by character
- <kbd>V</kbd> Visual mode that allows to select line by line

- **Keybinding**
  - <kbd>d</kbd> Deletes the selected (highlighted) text (You always can undo the deletion using ```u``` when swtching to normal mode \
  - <kbd>y</kbd> Copy a text to the clipboard 
  - <kbd>yy</kbd> or </kbd>Y</kbd> Copy the entire line 
  - <kbd>p</kbd> - paste a text to the editor below the current line 
  - <kbd>P</kbd> - Paste the text to the editor above the current line 
  - <kbd>c</kbd> - remove the highlighted text and switchs to insert mode
  - <kbd>r</kbd> - replace a single character

## Searching

- ```/myword``` - search for ```myword``` inside the next
- <kbd>n</kbd> Search for the next occurence
- <kbd>N</kbd> Search for the previous occurrence
- ```:%s/character/symbol/g``` Replace the word character by symbol (global).
To remove only a particular thing just select the text.


## Waypoint 
- <kbd>ma</kbd> - Mark this line a point to return if we want to go back just <kbd>'a</kbd>.
The character <kbd>a</kbd> is arbitrary, one can specify any character from the alphabet, or have multiples waypoints.

## Buffers
Buffers allow to have multiples files open in VIM in the command mode.

- ```:r [file_path]``` Read the contents of a file in the current file.
- ```:e [file_path]``` Open a new buffer
- ```:bn``` Go to the next buffer
- ```:bp``` Go to the previous buffer
- ```:enew``` A create a new empty buffer
