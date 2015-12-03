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

Create the horse class that we are using here.

```ruby
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

Create the MusicPlayer class that we are using here.

```ruby
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
