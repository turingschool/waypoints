# Build which

[Example video](FIXME) (have a student create this)

Which receives one argument, the name of a program.
It then looks through the directories in the `PATH`
environment variable, until it locates one that contains
the program. It prints that directory name out.

1. Look at how the real `which` works.

  ```
  $ which git
  /usr/local/bin/git
  ```
2. Now make your own that works the same way

  ```
  $ ruby which.rb git
  /usr/local/bin/git
  ```

Once you master this
--------------------

Add the ability to take a `-a` flag,
which tells it to list all the examples it finds.

```
$ ruby which.rb git
/usr/local/bin/git

$ ruby which.rb -a git
/usr/local/bin/git
/usr/bin/git
```

