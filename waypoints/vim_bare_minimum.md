Vim Bare Minimum
================


Notation: "C-a" means "hold control and press 'a'"

Vim is a mediocre text editor with a powerful, optimized, and mostly
consistent interface for expressing the edits you want to make.

Note that you will inevitably have to use vim at some point, even if only to quit.
For example 1: when you type `$ git commit` without a `-m` flag, you wind up in
vim unless you set a different text editor.
Fortunately, there's only about 8 things to learn the minimum set of functionality
(the 4 directions you can move in, edit, stop editing, save, and quit).

It is not necessary, or even important to use vim.
It is, however, very important to learn whatever editor you do choose to use,
eg if you use Atom, you should be proficient in Atom.
That siad, if you want to learn vim, this is what I suggest:

1. Watch [this 8 minute video](https://www.youtube.com/watch?v=ke7SfUFvvxo)
   that tells you how to approach learning vim. Ignore the cheatsheet he links.
2. Make it your goal to do the rest of these steps in less than 30 minutes.
   That will help you prioritize (its best to tackle vim in tiny pieces,
   just learn the ones that they describe)
3. Get out 2 pieces of paper and a pencil.
4. The minimal set of commands:
   Run `$ vimtutor` at the terminal, and as you go through the
   first lesson (It's the bare bare essentials: moving the cursor,
   editing a file, saving a file, deleting text, inserting text).
   On the first paper, write down all the things you learn as you go through vimtutor.
5. Cheatsheet: After going through the first lesson of vimtutor, choose about 8 of the
   "most important" commands and write them on the other sheet of paper,
   that will be your cheatsheet.
6. The Keybinding Queue:
   Learn the keys from the cheatsheet as Ben says to in the video,
   and as you find that you use them without needing the cheatsheet,
   erase them from the cheatsheet and put a checkmark on the big list
   to signify that you have "learned that one". Look through the list,
   choose one that seems like it should be useful, and copy it onto your cheatsheet
   to take the place of the one you have learned.
7. Configure: Use vim to edit the file `.vimrc` in your home directory
   (this file may or may not already exist) `$ vim ~/.vimrc`
   Paste this configuration into it (NOTE: you need to be in insert mode to paste)
   If you want more, I put a few I really like into
   [this](https://gist.github.com/JoshCheek/be4a372bdc1f6b3e64dd#file-2-additional-vimrc-settings-i-like-vim)
   file, take any that you like :)

   ```vim
   "" ===== Smallest reasonable configuration =====
   set nocompatible                " Behave more usefully at the expense of backwards compatibility (this line comes first b/c it alters how the others work)
   set encoding=utf-8              " Format of the text in our files (prob not necessary, but should prevent weird errors)
   filetype plugin on              " Load code that configures vim to work better with whatever we're editing
   filetype indent on              " Load code that lets vim know when to indent our cursor
   syntax on                       " Turn on syntax highlighting
   set backspace=indent,eol,start  " backspace through everything in insert mode
   set expandtab                   " When I press tab, insert spaces instead
   set shiftwidth=2                " Specifically, insert 2 spaces
   set tabstop=2                   " When displaying tabs already in the file, display them with a width of 2 spaces
   ```

That should get you started. If you're curious about where the hjkl came from,
it was created on this terminal:

![terminal key hjkl](http://www.catonmat.net/images/why-vim-uses-hjkl/adm-3a-hjkl-keyboard.jpg)

![terminal full view](http://www.catonmat.net/images/why-vim-uses-hjkl/lsi-adm-3a.jpg)

[Source](http://www.catonmat.net/blog/why-vim-uses-hjkl-as-arrow-keys/)
