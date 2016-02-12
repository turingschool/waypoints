# Build grep/ag

[Example video](https://vimeo.com/155066669)

Grep is a program that prints each line of its standard input, if it contains the characters in its arguments.
Ag is the same program, but done much better (highlights matches, and dramatically quicker).

Create your own grep program:

1. Look at `$ cat /etc/passwd`
1. Use `ag` or `grep` to filter results:

  ```
  $ cat /etc/passwd | ag ant
  _installassistant:*:25:25:Install Assistant:/var/empty:/usr/bin/false
  _krbtgt:*:217:-2:Kerberos Ticket Granting Ticket:/var/empty:/usr/bin/false
  _krb_krbtgt:*:230:-2:Open Directory Kerberos Ticket Granting Ticket:/var/empty:/usr/bin/false
  ```
1. Write your own grep:

  ```
  $ cat /etc/passwd | ruby grep.rb ant
  _installassistant:*:25:25:Install Assistant:/var/empty:/usr/bin/false
  _krbtgt:*:217:-2:Kerberos Ticket Granting Ticket:/var/empty:/usr/bin/false
  _krb_krbtgt:*:230:-2:Open Directory Kerberos Ticket Granting Ticket:/var/empty:/usr/bin/false
  ```
