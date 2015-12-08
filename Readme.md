Waypoints
=========

Waypoints are short practical demonstrations of a skill / topic.

So you think you're going to sit through a 3 hour class and come away with some skill?
During hours 2 and 3, you're just building on a shaky foundation.
I can't do that, hell I can't even read a blog and remember what the topic or takeaways were,
hell I can't even read (I'm dictating this to a stenographer).

Ability is the currency of comprehension, not notes.
So take notes to help you, but at the end of the day,
you need to perform something to solidify that knowledge.
That's what waypoints are for.

Setup
-----

You can do this however you like, but for simplicity, I'll define a structure you can follow unless you have some reason not to:

* Make a directory called `waypoints` in your `turing` directory: `$ mkdir ~/turing/waypoints`
* Go to that directory `cd ~/turing/waypoints`
* For each of the lessons below, you can make a directory to practice the waypoints in, eg for the "How testing works" lesson:

  ```sh
  $ cd ~/turing/waypoints
  $ mkdir how-testing-works
  $ cd how-testing-works
  ```

The Waypoints
-------------

### [How testing works](https://github.com/turingschool/lesson_plans/blob/master/ruby_01-object_oriented_programming_with_ruby/how_testing_works.markdown)

* [Material](https://github.com/JoshCheek/how-to-test)

Waypoints

* Make the file `test/example_test.rb`
* In that file, make two classes, `PassingTest` and `NonPassingTest`
* Give `PassingTest` one test, which passes
* Give `NonPassingTest` class a failing test, an erroring test, and a skipped test that would fail if it weren't skipped.
* [Example Video](https://vimeo.com/147628364)


### [Object Oriented Programming](https://github.com/turingschool/lesson_plans/blob/master/ruby_01-object_oriented_programming_with_ruby/object_oriented_programming.markdown)

[Example Video](https://vimeo.com/147760405)

#### Waypoint 1

Fill in the methods on the Horse class so that the examples below work.

```ruby
class Horse
  def initialize
  end

  def galloping?
  end

  def gallop
  end

  def rest
  end
end

bessie = Horse.new
anakin = Horse.new

bessie.galloping? # => false
anakin.galloping? # => false

bessie.gallop
bessie.galloping? # => true
anakin.galloping? # => false

bessie.rest
anakin.gallop
bessie.galloping? # => false
anakin.galloping? # => true
```

#### Waypoint 2

Fill in the methods on the MusicPlayer class so that the examples below work.

```ruby
class MusicPlayer
  def initialize(songs)
  end

  def playing
  end

  def play(track)
  end
end

songs = ['Born This Way', 'Shake It Off', 'Sandstorm']

mp = MusicPlayer.new songs
mp.playing # => "Born This Way"

mp.play 2
mp.playing # => "Sandstorm"

mp.play 0
mp.playing # => "Born This Way"

mp.play 1
mp.playing # => "Shake It Off"
```


### [Linked Lists](https://github.com/turingschool/curriculum/blob/master/source/projects/linked_lists.markdown)

[Example Video](https://vimeo.com/148098899)

Make a linked list with the data `"a",` `"b"`, `"c"`. Each node in the list is an array of length 2,
the first element being the data, the second being the link. Show that you can access each String.

Same thing, but with a hash table whose keys are `:data` and `:link`.

Same thing, but with an object that has methods `data` and `link`.


### [How Git Works](https://github.com/turingschool/lesson_plans/blob/master/ruby_01-object_oriented_programming_with_ruby/choose_your_own_adventure_intro_to_git.markdown)

[Example Video](http://www.example.com)

How I learned to stop fearing git: run `git status` after everything I do.
Do that here, even though I haven't explicitly listed it.

```
# Creating a repo
Create a directory                      # mkdir how-git-works
change into that directory              # cd how-git-works
init the repository                     # git init

# Adding new content
show the status                         # git status
Make 2 empty files                      # atom .
show the status                         # git status
add the 2 files                         # git add file1 file2
show the status                         # git status
commit the 2 files                      # git commit -m 'Add file1 and file2'
show the status                         # git status

# Seeing changes and editing content
show the status                         # git status
edit both files
show the status                         # git status
diff the first file                     # git diff file1
show the status                         # git status
add the first file                      # git add file1
show the status                         # git status
commit the fist file                    # git commit -m 'Add file1
show the status                         # git status

add the second file                     # git add file2
show the status                         # git status
commit the second file                  # git commit -m 'Add file2'
show the status                         # git status

# Adding some of the content
edit both files
show the status                         # git status
diff the first file                     # git diff file1
show the status                         # git status
add the first file                      # git add file1
show the status                         # git status
diff the first file                     # git diff file1
show the status                         # git status
diff the cached file                    # git diff file1 --cached
show the status                         # git status
commit the first file                   # git commit -m 'Add file1'
show the status                         # git status

# Disregarding a change
show the status                         # git status
diff the second file                    # git diff file2
show the status                         # git status
add the second file                     # git add file2
show the status                         # git status
diff the cached files                   # git diff --cached
show the status                         # git status
unadd (unstage) the second file         # git reset HEAD file2
show the status                         # git status
throw the second file's changes away    # git checkout -- file2
show the status                         # git status

# Viewing logs
Show the log of changes                 # git log
```
