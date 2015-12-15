# Character Counting

Solve [this challenge](https://github.com/turingschool/challenges/blob/master/character_count.markdown)
in the same way as I do in [This Video](https://vimeo.com/139372804).

Your goal is to think through the same considerations in the same contexts
and make the same decisions.

The purpose is to show how to start a project using BDD,
how to test using TDD, there's also some examples of pry and seeing is believing.

```
00:00 figure out what we're doing
02:40 Determine what success looks like
03:30 Translate to acceptance tests
07:00 Prove acceptance test by hard-coding result
08:00 Pseudocode highest layer
08:23 Implement highest layer
10:20 Discover the interface I need to unit test
12:00 Begin unit tests: Describe how the class works
13:40 Turn descriptions into tests
14:35 Prevent integration code from running during unit tests
16:15 Erroneously start writing tests at the bottom
17:10 Put that on hold, start testing at the top
18:00 Confirm idea by extracting to Seeing Is Believing
19:55 Update descriptions with feedback from implementation
20:20 Using --fail-fast to stop tests after first failure
20:30 Implementing toplevel of CountCharacters by using things that would make it easy
21:20 Create the foundation we built on top of
22:18 Using pry to gain context and try things out
23:13 `ls` in pry tells us what things we can do
24:50 Copy solution from pry into the method and edit it
25:45 Use test failure to direct our attention
27:30 Delete low-level test we don't need
28:40 Tests on edge cases
29:20 Break code to prove that passing tests actually work
30:15 Delete useless / painful acceptance test
31:20 Refactor CountCharacters
31:50 Delete redundant comments
32:22 Inline local variables that serve no purpose
33:15 Try out a refactoring to see if it's better, it's not, so defactor
34:45 Farewell
```
