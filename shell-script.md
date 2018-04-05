/*
Title: Shell Script
Decription: Shell Script
Author: Bhaskar Mangal
Date: 
Tags: Shell Script
*/

# Shell Script

## Tricks

1. How do I search a file for a particular linem then comment out using a bash script?

## Multipile line: comment and un-comment
- https://stackoverflow.com/questions/1676632/whats-a-quick-way-to-comment-uncomment-lines-in-vim
- https://stackoverflow.com/questions/2462794/indent-or-comment-several-text-lines-with-vi

down vote
For those tasks I use most of the time block selection.

Put your cursor on the first # character, press CtrlV (or CtrlQ for gVim), and go down until the last commented line and press x, that will delete all the # characters vertically.

For commenting a block of text is almost the same:

First, go to the first line you want to comment, press CtrlV. This will put the editor in the VISUAL BLOCK mode.
Then using the arrow key and select until the last line
Now press ShiftI, which will put the editor in INSERT mode and then press #. This will add a hash to the first line.
Then press Esc (give it a second), and it will insert a # character on all other selected lines.
For the stripped-down version of vim shipped with debian/ubuntu by default, type : s/^/# in the third step instead.