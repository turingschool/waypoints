Vim First Steps
===============

[Example video](https://vimeo.com/153750394)

```
Open a new file
  $ vim somefile
Go into insert mode (optimized for typing)
  i
Type several lines of giberish
  skldjf ksldjf
  sdf sdkfjsldk
  sdlkfjksldfj
Go into normal mode (optimized for navigating)
  <Esc>
Go right, down, left, up
  ljhk
Go left and right a bunch
  lhlhlhlh
Go up and down a bunch
  jkjkjkjkj
Do this 5 times:
  Pick a character somewhere on the screen
  Go there using the hjkl keys
  Go into insert mode and add a character
  ic<Esc>
  PROTIP: Always go back to normal mode after making an edit
Save the file
  :w
Quit vim
  :q
Look to see the file is there
  $ ls -l
Remove the file
  $ rm somefile
Repeat until you can do the whole thing in under 3 minutes.
```
