# Build cat

[Exmple video](https://vimeo.com/148889578)

Cat is a program that receives filenames
and prints them out.
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
$ cat boring_work_stuff.md
My file extension is "md"
that means "markdown" to nearly everybody.
But that's my trick to divert inquiry...
for me, "md" implies "my diary"

$ cat boring_work_stuff.md mydir/myfile.txt
My file extension is "md"
that means "markdown" to nearly everybody.
But that's my trick to divert inquiry...
for me, "md" implies "my diary"
i am quite sure
that within mydir
resides myfile,
patiently immobile
```

Build your own cat:

```sh
$ ruby cat.rb boring_work_stuff.md
My file extension is "md"
that means "markdown" to nearly everybody.
But that's my trick to divert inquiry...
for me, "md" implies "my diary"

$ ruby cat.rb boring_work_stuff.md mydir/myfile.txt
My file extension is "md"
that means "markdown" to nearly everybody.
But that's my trick to divert inquiry...
for me, "md" implies "my diary"
i am quite sure
that within mydir
resides myfile,
patiently immobile
```
