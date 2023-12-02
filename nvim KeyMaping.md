# VIM Basic Key commands
----
1. To delete from the cursor up to the next word:            dw
2. To delete from the cursor up to the end of the word:  de
3. To delete from the cursor to the end of a line:             d$
4. to delete a whole line type:                                           dd

5. To repeat a motion prepend it with a number:             2w
6. The format for a change command is:
	1. operator [number] motion
	2. where:
		1. operator - is what to do, such as d for delete
		2. [number] - is an optional count to repeat the motion
		3. motion - moves over the text to operate on, such as w (word), e( end of word) $ (end of line), etc
7. To move to the start of the line use a zero: 0
8. to under previous action, type:                                       u(lower)
	1. To undo all the changes on a line, type:                  U(Capt)
	2. To undo the undos, type:                                         CTRL-R



## The Put Command 
-----

1. To put back text that has just been deleted, type 'p'
	1. This puts the deleted text AFTER the cursor ( if a line was deleted it will go on the line below the cursor )
2. To replace the character under the cursor, type 'r' and then the character you want to have there
3. The change operator allows you to change from the cursor to where the motion takes you. eg. type `ce` to change from cursor to the end of the word, `c$` to change to the end of a line

# Cursor location and file status
----
1. CTRL-G displays your location in the file and the file status
	1. G moves to the end of the File.
	2. Number G moves to that line number
	3. gg moves to the first line
2. Typing `/` follow by a  phrase searches FORWARD for the phrase.
	1. typing `?` followed by a phrase searches BACKWARD for the phrases.
	2. After a search type `n` to find the next occurrence in the same dirrection CTRL-O takes you back to older positions, CTRI-I to newer positions
3. Typing `%` while the cursor is on a `(,), [,], {, or } ` goes to its match
4. To subsitute new for the first old in a line `:s/old/new`
	1. new for all 'old's on a line type           `:s/old/new/g`
	2. phrases between two line #'s type      `:#,#/old/new/g`
	3. all occurrences in the file type            `%s/old/new/g`
	4. to ask for confirmation each time add 'c'  `:%s/old/new/gc`

## How to exe an external cmd
-----

line 592
