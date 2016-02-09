# Build sort

[Example video](FIXME) (have a student create this)

Sort is a program that reads in each line of standard input,
sorts them alphabetically, and prints the sorted lines back out.

Create your own mv program:

1. Be able to generate random content:

  ```
  $ ruby -e '5.times { puts [*"a".."z"].sample*10 }'
  xxxxxxxxxx
  uuuuuuuuuu
  ffffffffff
  hhhhhhhhhh
  qqqqqqqqqq
  ```
1. Sort it using the real sort:

  ```
  $ ruby -e '10.times { puts [*"a".."z"].sample*10 }' | sort
  aaaaaaaaaa
  dddddddddd
  eeeeeeeeee
  iiiiiiiiii
  kkkkkkkkkk
  ```
1. Make your own sort program that does the same thing:

  ```
  $ ruby -e '10.times { puts [*"a".."z"].sample*10 }' | ruby sort.rb
  aaaaaaaaaa
  dddddddddd
  eeeeeeeeee
  iiiiiiiiii
  kkkkkkkkkk
  ```
