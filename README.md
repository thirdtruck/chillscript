# chillscript

## It's all cool, (dudette|dude)

A toy language that doesn't ask you to control anything, but to just enjoy the patterns.

## Requirements

* Ruby 2.0+ (Tested in Ubuntu Linux)

## Example

### examples/hello.chill
```
when greeting exists
and time-to-greet is true
  print greeting

when START-PROGRAM
  greeting becomes "Hello, World!"
  time-to-greet becomes true
```

### Usage
```
$ bin/chillscript examples/hello.chill
> Hello, World!
```

# The Language

chillscript is a pattern-matching language built around a state machine. When the conditions you ask about are met, chillscript will respond in the way you request. It will keep checking conditinos and responding as long as the responses changed conditions in some way (e.g. something that was false is now true).

# Patterns

## when [condition]

Creates a new pattern that matches against the given condition.

### when [variable] exists

Asks whether the variable has been set at all, regardless of its value.

### when [variable] is [state]

Asks whether the variable is in a given state. (Currently only works for true/false values.)

### when START-PROGRAM

A special pattern that is only run once and before anything else. The place to set up your initial conditions.

## and [condition]

Used after `when` to add more conditions to it.

# Responses

## print [variable]

Prints the value of the variable to the screen.

## [variable] becomes [value]

Changes the value of the variable. **(`becomes` will almost certainly be replaced with a shorter word.)**

# Variables

Variable names need to start with a number or letter, and can be followed by any number of number, letters, or dashes. **(Variable names much more specific very soon!)**

# Parting Notes

The language doesn't make any attempt to detect infinite loops, so be careful!
