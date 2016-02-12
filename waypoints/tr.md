# Build tr

[Example video](https://vimeo.com/155066660)

Tr is a program that takes two arguments,
a string of characters to replace,
and a string of characters to replace them with.

1. See tr in action:

  ```
  $ echo abracadabra | tr a A
  AbrAcAdAbrA

  $ echo abracadabra | tr ac AC
  AbrACAdAbrA
  ```
1. Write your own tr:

  ```
  $ echo abracadabra | ruby tr.rb a A
  AbrAcAdAbrA

  $ echo abracadabra | ruby tr.rb ac AC
  AbrACAdAbrA
  ```
