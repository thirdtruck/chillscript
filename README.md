# chillscript

## It's all cool, (dudette|dude)

A toy language that has no control statements, only reactions to states.

## Examples

`
when greeting exists
and time-to-greet is true
  print greeting

when START-PROGRAM
  greeting becomes "Hello, World!"
  time-to-greet becomes true
`

`
$ chillscript hello.chill
> Hello, World!
`
