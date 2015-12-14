Answers placed one after the question.

### Q1.

What does it mean if I say

```
$ which ruby
/Users/josh/.rubies/ruby-2.1.1/bin/ruby
```


### Q2.

What does it mean? If I say

```
$ ruby ./hello_world.rb lol
You said lol
```


### A1.

The dollar sign means we're entering this at the shell, the shell will turn it into the array `["which", "ruby"]`,
and it will go run the program `which`, handing it the arguments `["ruby"]`. This program will look in all the places
that programs can be, until it finds one named `ruby`. The second line is what the program printed: the location of Ruby.


### Q3.

Make the program from #2


### A2.

The dollar sign means we're entering this at the shell, the shell will turn it into the array `["ruby", "./hello_world.rb", "lol"]`,
and it will go run the program `ruby`, handing it the arguments `["./hello_world.rb", "lol"]`. Ruby will then go look for the file
`./hello_world.rb`, where the dot means that it looks in the current directory for a file named `hello_world.rb`. When it finds that
program, it will set the constant `ARGV` to `["lol"]` and run the code in the file. The second line, "You said lol" is what the program
printed.


### Q4.

Do all ruby files end in `.rb`?


### A3.

```ruby
puts "You said #{ARGV[0]}"
```


### Q5.

Is this possible?

```
$ ruby ./index.html lol
You said lol
```


### A4.

No, the extension means nothing, we just choose to put them there so that we know it should be Ruby code in the file.
But nothing forces it to actually be Ruby code.


### Q6.

Why do you not see the example in #5?


### A5.

Yes, if we put Ruby code in `index.html`


### Q7.

Is the input filename always the first argument to the program?


### A6.

Because by naming it `index.html`, we're telling the world that the code in the file is html code... but it's not, it's Ruby code.
This would be really confusing for people.


### Q8.

A file is just a...


### A7.

No, it's totally arbitrary, the arguments have no meaning except that the program does things with them that gives them meaning.


### Q9.

What are each of these?

```ruby
a
self.a
a()
self.a()
:a
"a"
A
a 1
a(1)
self.a(1)
@a
$a
def
1
11111111111111111111111111111111111111111111111111111111111
a = 1
self.a = 1
1.23
```

### A8.

A string on your hard drive


### Q10.

What is this:

```ruby
puts
```


### A9.

```ruby
a          # maybe a local variable, maybe a method
self.a     # a method named a, being called on self
a()        # a method named a, being called on self
self.a()   # a method named a, being called on self
:a         # the Symbol a
"a"        # the String a
A          # the constant A
a 1        # a method named a, being called on self with one argument, the Fixnum 1
a(1)       # a method named a, being called on self with one argument, the Fixnum 1
self.a(1)  # a method named a, being called on self with one argument, the Fixnum 1
@a         # the instance variable a
$a         # the global variable a
def        # a keyword that creates a method
1          # the Fixnum 1
11111111111111111111111111111111111111111111111111111111111 # the Bignum 1
a = 1      # setting the local variable a to 1
self.a = 1 # calling the method a= on self with one argument, the Fixnum 1
1.23       # the Float 1.23 (one and twenty three hundredths)
```


### Q11.

What is this:

```ruby
require "minitest/pride"
```


### A10.

Either a local variable or a method (based on context, it's probably a method)



### Q12.

If we ran this code, what will happen?

```ruby
lol
```


### A11.

A method named `require`, being called on `self`, with one argument, the String `"minitest/pride"`.
That method will go look in places that Ruby keeps code, until it finds the file `pride.rb` in a directory
named `minitest`, and it will assume the code in that file is Ruby, and evaluate it.


### Q13.

If we ran this code, what will happen? Describe it with as much detail and precision as you can.

```ruby
def lol(lol)
  lol
end
lol = 123
lol lol
```


### A12.

It will raise an undefined local variable or method.


### Q14.

What does this line mean?

```
$ gem install redcarpet
Fetching: redcarpet-3.3.2.gem (100%)
Building native extensions.  This could take a while...
Successfully installed redcarpet-3.3.2
1 gem installed
```


### A13.

```ruby
1 def lol(lol)
2   lol
3 end
4 lol = 123
5 lol lol
```

* Line 1: define the method `lol`.
* Line 4: define the local variable `lol`, which points at the Fixnum `123`,
* Line 5: the left `lol` must be a method, because we're giving it an argument, the right `lol` is either a
  method or a local variable, Ruby looks for local variables first, so it finds the local variable `lol` that
  we assigned on line 4, and passes that as an argument to the method `lol`. To call the method `lol`, it looks
  on `self`'s class, `self` is main, so its class is Object, which is where the method `lol` was defined.
  It adds a new binding, sets `self` to main. It sets the return value to `nil`.
* Line 1: Because there is one argument, `lol`, it sets that, in the new binding, to point at the `123` that we gave it on line 5.
* Line 2: it sees `lol`, which is either a local variable or a method.
  It looks for the local variable, and finds the one defined as an argument on line 1, looks it up and finds `123`.
  Because line 2 evaluated to `123`, it sets the return value to `123`.
* Line 3: The method is over, so it pops the binding off the stack and returns to line 5 with the return value of `123`
* Line 5: So line 5 evaluates to `123`. The program ends.


### Q15.

What does the program `cat` do?


### A14.

The dollar sign implies the "prompt" (mine is a fish, yous is probably bash or zsh), so we run it at the shell.
It will find the program `gem` and set its arguments to `["redcarpet"]`
The program `gem` will go find `redcarpet` and install it, printing out information that says this, as it does so.


### Q16.

Where are the programs `cat` and `gem` located?


### A15.

It prints out files.


### Q17.

What does the program `pwd` tell you? (if you don't know, don't search for it,
instead try it and see, then make a hypothesis about what it does,
and think of a way to test that the hypothesis is correct)


### A16.

There is a program, `which`, that tells you where other programs are located.

```sh
$ which cat
/bin/cat

$ which gem
/Users/josh/.rubies/ruby-2.2.3/bin/gem
```

### Q18.

Cat out a file, lets say it's called `my_input.markdown`, so: `$ cat my_input.markdown`
(swap the name with whatever your file's name happens to be)

Without asking anyone or looking the answer up, take a guess at what you think this will do: `$ cat my_input.markdown my_input.markdown`
If you guessed incorrectly, devise experiments until you understand what it does.


### A17.

It prints out the directory you are in. You can verify it by `cd`ing to different directories and running `pwd` to see it give back different values.


### Q19.

You can render markdown with `redcarpet` like this:

```ruby
require 'redcarpet'                           # => true
renderer = Redcarpet::Render::HTML.new        # => #<Redcarpet::Render::HTML:0x007fe934876c78>
markdown = Redcarpet::Markdown.new(renderer)  # => #<Redcarpet::Markdown:0x007fe9348769d0 @renderer=#<Redcarpet::Render::HTML:0x007fe934876c78>>
markdown.render('# omg')                      # => "<h1>omg</h1>\n"
```

Go write [Chisel](http://tutorials.jumpstartlab.com/projects/chisel.html)
by cheating and using redcarpet instead of making your own parser.
You succeed once this code works:

```
$ ruby ./lib/chisel.rb my_input.markdown my_output.html
Converted my_input.markdown (6 lines) to my_output.html (6 lines)
```


### A18.

It prints out each program in its `ARGV`


### A19.

```ruby
input_filename  = ARGV[0]
output_filename = ARGV[1]

markdown = File.read input_filename

require 'redcarpet'
renderer = Redcarpet::Render::HTML.new
html     = Redcarpet::Markdown.new(renderer).render(markdown)

File.write(output_filename, html)

puts "Converted #{input_filename} (#{markdown.lines.count} lines) to #{output_filename} (#{html.lines.count} lines)"
```
