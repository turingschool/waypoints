# Build Chisel

Chisel is a program that converts Markdown to HTML.
There's a while project around it, but we're going to cheat
and use redcarpet, a markdown parser.

## Install Redcarpet

```
$ gem install redcarpet
Fetching: redcarpet-3.3.3.gem (100%)
Building native extensions.  This could take a while...
Successfully installed redcarpet-3.3.3
```

## Make sure you can use Redcarpet
```
require 'redcarpet'
renderer = Redcarpet::Render::HTML.new
markdown = Redcarpet::Markdown.new(renderer)
markdown.render("# hello")
# => "<h1>hello</h1>\n"
```

## Make a markdown file

Save this in `input.md`

```
# My Life in Desserts

## Chapter 1: The Beginning

"You just *have* to try the cheesecake," he said. "Ever since it appeared in
**Food & Wine** this place has been packed every night."
```

## Make Chisel

Write a program that does this:

```
$ ls
chisel.rb input.md

$ ruby chisel.rb input.md output.md
Converted my_input.markdown (6 lines) to my_output.html (8 lines)

$ ls
chisel.rb input.md output.md

$ cat output.md
<h1>My Life in Desserts</h1>

<h2>Chapter 1: The Beginning</h2>

<p>&quot;You just <em>have</em> to try the cheesecake,&quot; he said. &quot;Ever since it appeared in
<strong>Food &amp; Wine</strong> this place has been packed every night.&quot;</p>
```
