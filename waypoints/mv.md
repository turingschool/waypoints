# Build mv

[Example video](http://showterm.io/e6b334be3f3f39e532325)

Mv is a program that receives two filenames.
The first is the name of the file to move.
The second is the name of the place to move it to.

Create your own mv program:

1. Make a file, 'file1', with something in it.
1. Run `$ mv file1 file2`
1. Use `ls` to see that there is no file1, there is a file2
1. Use `cat` to see that file2 contains what you put into file1
1. Write your own mv that works the same way: `$ ruby mv.rb file2 file3`
