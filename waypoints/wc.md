# Build wc

wc is a program that receives filenames
and prints out how many lines, words, and characters are in each file.

Make these two files:

* Your directory structure should look like this:

  ```
  $ tree
  .
  ├── mydir
  │   └── myfile.txt
  └── boring_work_stuff.md
  ```
* `boring_work_stuff.md`

  ```
  My file extension is "md"
  that means "markdown" to nearly everybody.
  But that's my trick to divert inquiry...
  for me, "md" implies "my diary"
  ```
* `mydir/myfile.txt`

  ```
  i am quite sure
  that within mydir
  resides myfile,
  patiently immobile
  ```


```sh
$ wc somefile.md
       4      24     142 somefile.md

$ wc somefile.md mydir/myfile.txt
       4      24     142 somefile.md
       4      11      69 mydir/myfile.txt
       8      35     211 total
```

Build your own wc:

```sh
$ ruby wc.rb somefile.md
       4      24     142 somefile.md

$ ruby wc.rb somefile.md mydir/myfile.txt
       4      24     142 somefile.md
       4      11      69 mydir/myfile.txt
       8      35     211 total
```
