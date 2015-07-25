# chillscript

## It's all cool, (dudette|dude)

A toy language that doesn't ask you to control anything, but to just enjoy the patterns.

chillscript exists to help you learn about state machines and pattern matching (and, incidentally, to help the author/contributors learn about language design). It's intended for people who want to learn about and experiment with such concepts without having to figure out the nuances of a much more complicated language.

### Guiding principles

In order:

1. Writing and reading the language is fun and edifying.
2. Only One Thing Happens, or *OOTH*. (Explained below.) 
3. Writing and reading the language is fun. (Repeated for emphasis.)

### Only One Thing Happens (OOTH)

Only One Thing Happens when you can tell exactly what is going to occur next in a program by knowing nothing but the (ideally simple) state of the machine and the current line in the program. Features like efficient syntax, parallalization, optimized caching, etc. are secondary to a surprise-free reader experience.

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

chillscript is a pattern-matching language built around a state machine. When the conditions you ask about are met, chillscript will respond in the way you request. It will keep checking conditions and responding to them as long as the responses change conditions in some way (e.g. something that was false is now true). If all of the patterns are checked in a single pass and the state machine remains unchanged, then the program will finish.

# Patterns

A pattern start with a single `when` line, then zero or more `and` lines, and are followed by one or more responses to the pattern. Patterns are separated by blank lines.

## when [condition]

Creates a new pattern that matches against the given condition. Conditions are described below.

### when [variable] exists

Asks whether the variable has been set at all, regardless of its value.

### when [variable] is [state]

Asks whether the variable is in a given state. (Currently only works for true/false values.)

### when START-PROGRAM

A special pattern that is only run once and before anything else. The place to set up your initial conditions.

## and [condition]

Used after the first `when` to add more conditions to to the pattern. A pattern can have any number of these.

# Responses

Each pattern needs at least one response, which tells the program what to do when the state machine matches the pattern. Each response is indented by two spaces.

## print [variable]

Prints the value of the variable to the screen.

## [variable] becomes [value]

Changes the value of the variable. Currently, *value* can be `true`, `false`, or a string wrapped in double quotes ("). **(`becomes` will almost certainly be replaced with a shorter word.)**

# Variables

Variable names need to start with a number or letter, and can be followed by any number of number, letters, or dashes. **(Expect variable names to be much more specific very soon!)**

# Parting Notes

The language doesn't make any attempt to detect infinite loops, so be careful!
