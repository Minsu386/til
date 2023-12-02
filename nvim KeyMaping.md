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
