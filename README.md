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

```h``` - right \
```j``` - down \
```k``` - up \
```l``` - left

- **Keybinding**
  - ```u``` - Undo changes (After edit the file and perhaps you want to undo the changes, switch to normal mode and undo)
  - ```ctrl + r``` - Redo
  - ```cc``` - Removes the content of the line and enters in the insert mode
  - ```D``` - Remove everything after the cursor
  - ```dd``` - deletes the whole line
  - ```w``` or ```W``` - jump to the next word (Something separated by space)
  - ```b``` - jump to the previous word (backwords)
  - ```0``` - sends the cursor to the begining of the line 
  - ```$``` - sends the cursor to the end of the line
  - ```d0``` - Delete from the cursor to the beginning of the line
  - ```d$``` - Delete from the cursor to the end of the line
  - ```ci""``` - Find the nearest quote signal, remove the content inside quote "" and start the insert mode between the empty quote. Very useful when we intend to remove a text and replace for a new one.
  - ```ci(``` - Find the nearest openning paranthesis, remove the content and enters the insert mode to start write inside the paranthesis. Very useful to remove the arguments of function and start writing new ones
  - ```Line#G``` - Go to Line#
  - ```dw``` - delete the next word 
  - ```db``` - delete the previous word
  - ```diw``` - delete in the middle of the word (delete the current work when the cursor is in the middle of it)
  - ```%``` - takes the cursor to the pairing closing parenthesis, curly brackets etc.
  - ```==``` - indent a line
  - ```gg``` - Go to the begin of the file 
  - ```G``` - Go to the end of the file 
  - ```gg=G``` - Indent the entire file

**We can combine numbers and keybinding, that multiplies the action
ex: 5k takes 5 lines up, 5h goes 5 characters right, 2u undo 2 times**

## Insert mode 
In the insert mode, whatever is written has no functionality and is just a text!. That means that any keyboard that we press when in the insert mode, is written in the file. There are many ways to enter in the insert mode:

```i``` - Start the insert mode where the cursor is \
```I``` - Start in the insert mode placing the cursor at the begining of the line \
```a``` - Start the insert mode, one character after the cursor current position(append) \
```A``` - Start the insert mode placing the cursor at the end of the line \
```o``` - Start the insert mode opening a newline below the current line (open new line) \
```O``` - Enter in the insert mode placing the cursor above the current line 

To leave the insert mode to the normal mode press ```esc```.

## Visual mode (For selecting)
The visual mode is for text selection. There are three visual modes, but here I mention only two:
- ```v``` - Start visual mode, and allows to select character by character
- ```V``` - Visual mode that allows to select line by line

- **Keybinding**

```d``` - Deletes the selected (highlighted) text (You always can undo the deletion using ```u``` when swtching to normal mode \
```y``` - copy a text to the clipboard \
```yy``` or ```Y``` - Copy the entire line \
```p``` - paste a text to the editor below the current line \
```P``` - Paste the text to the editor above the current line \
```c``` - remove the highlighted text and enter in teh insert mode (change) \
```r``` - replace a character

## Searching

 - ```/myword``` - search for ```myword``` inside the next
- ```n``` - next occurence
- ```N``` - previous occurrence
- ```:%s/character/symbol/g``` - Replace the word character by symbol (global).
To remove only a particular thing just select the text.


# waypoint 
```ma``` - Mark this line a point to return if we want to go back just ```'a```.
The character ```a``` is arbitrary, one can specify any character from the alphabet, or have multiples waypoints.
