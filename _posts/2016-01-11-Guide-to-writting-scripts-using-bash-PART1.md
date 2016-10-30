---
layout: post
title: Guide to writting scripts using bash [PART1]
comments: True
summary:
status: draft
hn-discussion:
---

### A Simple Shell Script
A shell script is little more than a list of commands that are run in sequence. Conventionally, a shellscript should start with a line such as the following:
> #!/bin/bash
This indicates that the script should be run in the bash shell regardless of which interactive shell the user has chosen. This is very important, since the syntax of different shells can vary greatly.

### A simple example
Here's a very simple example of a shell script. It just runs a few simple commands
```
#!/bin/bash
echo "Hello, $USER."
```
Firstly, notice the comment on line 4. In a bash script, anything following a pound sign # (besides the shell name on the first line) is treated as a comment. ie the shell ignores it. It is there for the benifit of people reading the script.
**$USER** are  _variables_ . These are standard variables defined by the bash shell itself, they needn't be defined in the script. Note that the variables are expanded when the variable name is inside double quotes. _Expanded_ is a very appropriate word: the shell basically sees the string **$USER** and replaces it with the variable's value then executes the command.

### Variables
Any programming language needs variables. You define a variable as follows:
```
X="Hello"
```
and  refer to it as follows:
```
$X
```
More specifically, **$X** is used to denote the value of the variable X. Some things to take note of regarding semantics:
* bash gets unhappy if you leave a space on either side of the = sign. For example, the following gives an error message:
```
X = hello
```
* while I have quotes in my example, they are not always necessary. where you need quotes is when your variable names include spaces. For example,
```
X=hello world # error
X="hello world" # OK
```
This is because the shell essentially sees the command line as a pile of commands and command arguments seperated by spaces. foo=baris considered a command. The problem with foo = bar is the shell sees the word foo seperated by spaces and interprets it as a command. Likewise, the problem with the command X=hello world is that the shell interprets X=hello as a command, and the word "world" does not make any sense (since the assignment command doesn't take arguments).

_TO BE CONTINUED_
