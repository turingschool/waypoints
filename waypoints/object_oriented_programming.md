# [Object Oriented Programming](https://github.com/turingschool/lesson_plans/blob/master/ruby_01-object_oriented_programming_with_ruby/object_oriented_programming.markdown)

[Example Video](https://vimeo.com/147760405)

## Waypoint 1

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

## Waypoint 2

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
