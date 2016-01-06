# Require and the Load Path

[Material](https://github.com/turingschool/lesson_plans/blob/master/ruby_01-object_oriented_programming_with_ruby/load_path_and_require.markdown)

[Example video](https://vimeo.com/150878262)

## Waypoint

Go to the minitest gem on your computer
(find it with `$ gem which minitest`, then cd there).


## Setup

We're going to change which files get required.
Make this structure, the comments show what goes in each file:

```
.
├── lib
│   ├── bbq
│   │   └── yolo.rb   # puts "DGAF, YOLOIN IT UP!"
│   ├── lol
│   │   └── yolo.rb   # puts "YOLO, MOFO!"
│   │── ttyl.rb       # require "yolo"
│   └── ttfn.rb       # puts "ta ta for now"
└── test
    └── wat.rb        # require "ttfn"
```


## Waypoints

* Run `$ ruby test/wat.rb`, it should fail. Then fix the load path
  with the `-I` flag and run again to see it print "ta ta for now".
* Run `$ ruby test/wat.rb`, it should fail. Then fix the load path
  by editing `$LOAD_PATH` in wat.rb variable and run again to see
  it work.
* Run `$ ruby lib/ttyl.rb`, it should fail. In any way you like
  (ie `-I` or editing the `$LOAD_PATH`), have its require
  statement find `lib/lol/yolo.rb`, so it should print
  "YOLO, MOFO!".
* Same as above, but now have it find `lib/bbq/yolo.rb`, so it
  should print "DGAF, YOLOIN IT UP!".
* Run `$ ruby lib/ttyl.rb` and have its require statement find
  `lib/lol/yolo.rb` when it exists (will print "YOLO, MOFO!"),
  and `lib/bbq/yolo.rb` when it doesn't
  (will print "DGAF, YOLOIN IT UP!").
