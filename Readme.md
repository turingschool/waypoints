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


### [Debugging]()

Find a failing test

```sh
$ mrspec centaur_test.rb --fail-fast
...lots of output...
rspec /Users/josh/deleteme/erroneous_creatures/centaur_test.rb:22 # Centaur it makes a horse sound when it runs
```

Edit the file

```sh
$ atom centaur_test.rb:22
```

Tag the failing test with "current" and pry just before the line in the test from the stacktrace

```ruby
meta current: true
def test_it_makes_a_horse_sound_when_it_runs
  centaur = Centaur.new("George","Palomino")
  require 'pry'
  binding.pry
  assert_equal "Clop clop clop clop!!!", centaur.run
end
```

Run the test tagged with "curent"

```sh
$ mrspec -t current
```

```ruby
    23: def test_it_makes_a_horse_sound_when_it_runs
    24:   centaur = Centaur.new("George","Palomino")
    25:   require 'pry'
 => 26:   binding.pry
    27:   assert_equal "Clop clop clop clop!!!", centaur.run
    28: end

[1] pry(#<CentaurTest>)>
```

Make sure it fails where you expect it to

```ruby
[1] pry(#<CentaurTest>)> centaur.run
NoMethodError: undefined method \`+' for nil:NilClass
from /Users/josh/deleteme/erroneous_creatures/centaur.rb:24:in `run'
```

Look at the method that is failing

```ruby
pry> show-source centaur.run

def run
 @crankiness += 1
 @crankiness < 3 ? "Clop clop clop clop!!!" : "NO!"
end
[3] pry(#<CentaurTest>)>
```

Go into the object that is breaking

```ruby
[3] pry(#<CentaurTest>)> self
=> #<CentaurTest:0x007feb061fe138 @NAME="test_it_makes_a_horse_sound_when_it_runs", @assertions=0, @failures=[]>
[4] pry(#<CentaurTest>)> cd centaur
[5] pry(#<Centaur>):1> self
=> #<Centaur:0x007feb061fdbc0 @breed="Palomino", @laying=false, @name="George", @sleeping=false, @standing=true>
[6] pry(#<Centaur>):1>
```

Look at the method again

```ruby
[7] pry(#<Centaur>):1> show-source run

def run
 @crankiness += 1
 @crankiness < 3 ? "Clop clop clop clop!!!" : "NO!"
end
```

Go through each line one at a time until you see what is wrong

```ruby
[8] pry(#<Centaur>):1> @crankiness += 1
NoMethodError: undefined method \`+' for nil:NilClass
from (pry):4:in \`__pry__'
[9] pry(#<Centaur>):1> @crankiness
=> nil
```

Think about why this could happen:
Did we choose the wrong instance variable?
Check for an instance variable that we might have misspelled

```ruby
[10] pry(#<Centaur>):1> ls -i
instance variables: @breed  @laying  @name  @sleeping  @standing
```

Maybe nothing ever set the variable?
Look at all the code to see where it maybe should have been set.

```ruby
[12] pry(#<Centaur>):1> cat centaur.rb
...
```

We see it in `sleep`, but that looks like it's resetting the variable
probably it should be set in initialize
So exit the test suite

```sh
Pry> exit!
```

And set crankiness in initialize

```sh
$ atom centaur.rb
```

```ruby
  ...
  @sleeping = sleeping
  @crankiness = 0
end
```

Now run the test again, and only exit pry, not the program
```sh
$ mrspec centaur_test.rb  -t current
```

```ruby
Centaur
From: /Users/josh/deleteme/erroneous_creatures/centaur_test.rb @ line 26 CentaurTest#test_it_makes_a_horse_sound_when_it_runs:

    23: def test_it_makes_a_horse_sound_when_it_runs
    24:   centaur = Centaur.new("George","Palomino")
    25:   require 'pry'
 => 26:   binding.pry
    27:   assert_equal "Clop clop clop clop!!!", centaur.run
    28: end

[1] pry(#<CentaurTest>)> exit
  it makes a horse sound when it runs

Failures:

Finished in 5.27 seconds (files took 0.4822 seconds to load)
1 example, 0 failures
```

Now remove the pry
