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

* How to program
  * [Object Oriented Programming](waypoints/object_oriented_programming.md)
  * [Linked Lists](waypoints/linked_lists.md)
  * [Character Counting](waypoints/character_counting.md) Shows how to start a project
* Testing
  * [How testing works](waypoints/how_testing_works.md) (the mechanics of how to test)
  * [Character Counting](waypoints/character_counting.md) Starting with high-level tests, moving down to unit tests.
* Files / command-line programs
  * [Quiz Week2](waypoints/quiz_week2.md)
  * [echo](waypoints/echo.md)
  * [cat](waypoints/cat.md)
  * [cp](waypoints/cp.md)
  * [wc](waypoints/wc.md)
  * [Chisel](waypoints/chisel.md)
  * [Writing pwd](waypoints/pwd.md)
* Pry / debugging
  * [Debugging With Pry](waypoints/debugging_with_pry.md)
  * [Discovering how to write PWD with pry](waypoints/pwd.md)
  * [Character Counting](waypoints/character_counting.md) uses pry to gain context and try things out
* Refactoring
  * [Blowing Bubbles 1](waypoints/blowing_bubbles1.md) Condense a bubble sort down to 1 line and back
  * [Blowing Bubbles 2](waypoints/blowing_bubbles2.md) Convert a procedural bubble sort to an object oriented bubble sort
  * [Character Counting](waypoints/character_counting.md) Refactoring a solution we create
