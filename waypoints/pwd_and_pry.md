# Build pwd, discovering how with pry

## Goal

Pwd is a program that prints where you are located on your computer.

```sh
$ pwd
/Users/josh/code/jsl/waypoints

$ cd ..
$ pwd
/Users/josh/code/jsl
```

Build your own pwd:

```sh
$ ruby pwd.rb
/Users/josh/Turing/waypoints/pwd_and_pry

$ ruby pwd_and_pry/pwd.rb
/Users/josh/Turing/waypoints
```

## Start at the top

Don't worry about what you don't know, just yet.
First, do the pieces you do know, so that you can
see exactly what it is you're looking for.

## Discovery with Pry

We know how to do some of the pieces, but not all of them.
To figure out the rest, we'll look around using pry.

* Note that you can use `ls` to look at something in pry
  eg `> ls -v String` and you can filter them with `--grep`

  ```ruby
  $ pry
  [1] pry(main)> ls -v String --grep case
  String#methods:
    casecmp  downcase  downcase!  swapcase  swapcase!  upcase  upcase!
  ```

* Note that you can read documentation if you

  ```
  $ gem install pry-doc
  Fetching: yard-0.8.7.6.gem (100%)
  Successfully installed yard-0.8.7.6
  Fetching: pry-doc-0.8.0.gem (100%)
  Successfully installed pry-doc-0.8.0
  2 gems installed
  ```

  And then use `show-doc` eg

  ```ruby
  $ pry
  [1] pry(main)> show-doc "lkj".upcase

  From: string.c (C Method):
  Owner: String
  Visibility: public
  Signature: upcase()
  Number of lines: 6

  Returns a copy of str with all lowercase letters replaced with their
  uppercase counterparts. The operation is locale insensitive---only
  characters ``a'' to ``z'' are affected.
  Note: case replacement is effective only in ASCII region.

     "hEllO".upcase   #=> "HELLO"
  [2] pry(main)>
  ```
* To figure out how to get the directory,
  write down some nouns might be associated with the task.
  Now we will go see if any of those nouns are available to us.
  The obvious place to start is `Object`, because it contains all the other methods.
  So try listing it out and using `--grep` to filter the results.
* When using `--grep`, you want to be imprecise enough to find
  the thing you're looking for, especially if there are spelling/capitalization
  differences, but precise enough to filter out things that you're not actually interested in.
* Now go exploring any of the things that look promising.
* When you eventually find it, drop it into your program!
