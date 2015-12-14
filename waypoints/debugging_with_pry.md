# [Debugging With Pry](https://github.com/turingschool/lesson_plans/blob/master/ruby_01-object_oriented_programming_with_ruby/debugging.markdown)

* [Here](https://github.com/turingschool/curriculum/blob/ecc5e440311bb1689f9e98db25a25f5ada20b480/source/topics/debugging/debugging.markdown#pry)
  are notes on what I think is most useful in Pry
* [Here](https://github.com/turingschool-examples/erroneous_creatures)
  are some mythical creatures with errors in them,
  that you can use to practice debugging.

## Waypoint

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
