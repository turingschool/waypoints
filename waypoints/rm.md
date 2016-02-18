# Build rm

[Example video](https://vimeo.com/155835416)

Rm is a program that receives filenames as arguments,
and deletes the specified files.

1. Use `touch` to make `file1`, `file2`, `file3`
1. Run `$ rm file1 file3`
1. Use `ls` to see that files 1 and 3 got deleted
1. Remake the deleted files
1. Write your own rm that works the same way: `$ ruby rm.rb file1 file3`
