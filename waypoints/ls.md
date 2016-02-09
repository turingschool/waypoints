# Build ls

[Example video](FIXME) (have a student create this)

Ls is a program that takes a path,
and lists out all the files that are located there.

1. List the contents of a directory

   ```
   $ mkdir -p a/b/c a/b/d
   $ touch a/b/file1 a/b/file2 a/b/c/file3 a/b/c/file4 a/b/d/file5 a/b/d/file6
   $ ls a/b
   c     d     file1 file2

   $ ls a/b/c
   file3 file4

   $ ls a/b/d
   file5 file6
   ```
1. Write your own ls. This is what mine looked like, yours can differ in details, but not functionality.

   ```
   $ ruby ls.rb a
   a/b

   $ ruby ls.rb a/b
   a/b/c	a/b/d	a/b/file1	a/b/file2

   $ ruby ls.rb a/b/c
   a/b/c/file3	a/b/c/file4

   $ ruby ls.rb a/b/d
   a/b/d/file5	a/b/d/file6
   ```
