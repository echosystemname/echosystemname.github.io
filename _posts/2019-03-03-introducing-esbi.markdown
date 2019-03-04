---
layout: post
title: "Introducing ESBI!"
date: 2019-03-03 00:00:00
categories: posts
---

ESBI (Echo's Shitty Brainfuck Interpreter) is a project I have started in order to get more familiar with lower level programming. As the name suggests, it is an interpreter for the esoteric programming language called brainfuck. 

## What is brainfuck?

Brainfuck is an esoteric programming language, which was created in 1993 by Urban Müller. It is brutally minimalistic, and was designed as a challenge to programmers, with the README to the first compiler ending with "Who can program anything useful with it? :)". Brainfuck is Turing complete (since it implements a Turing machine, which is the definition of being Turing complete), but it is not very practical to use as a general purpose language.

Brainfuck has only 8 commands, which describe the operation of a Turing machine. The main components are an infinite array containing bytes, and a cursor pointing to one element of that array. The 8 commands manipulate the cursor and the values of the array elements, and deal with I/O.

| Command	| Description|
| --- |:---:| ---:|
|`>` | Add one to the cursor (to point to the element on the right, assuming you read left-to-right)|
|`<` | Subtract one from the cursur (to point to the element to the left, assuming you read left-to-right)|
|`+` | Add one to the element at the current cursor position |
|`-` | Subract one from the element at the current cusor position |
|`.` | Print the ASCII value of the byte in the element at the current cursor position |
|`,` | Read in one byte of data, and place it in the element at the current cursor position |
|`[` | Start a loop which ends when the element at the current cursor position is zero (equivilent to starting a while loop) |
|`]` | Move back to the start of the loop |

## Why make ESBI?

It sounded interesting.

## Most interesting problem so far

The hardest part so far has been figuring out how to jump back to the start of a loop. I ended up just doing a bit of pre-processing to find out the start/end index of each loop in the source code. I think it could be cool to parse the code into a stack or tree structure, and then do an in-order traversal which would handle this problem. This solution would definitely be better if Brainfuck had logical branching (if/else) outside of loops. Maybe I'll build that in at some point. ;)

## Future of ESBI?

I'd like to keep hacking on this project, if the whim arrises. I'd like to make a debugger/editor, where you can write Brainfuck code, and then step forwards and backwards through it, while being able to inspect the contents of the infinite array and cursor location. I could then start to add macros or extensions to brainfuck to add features. This would mean it's not *officially* compliant with Brainfuck, but I'm doing this for my own education and enjoyment, so I think it's fine.


## Show me the code!!

[The code can be found here!](https://github.com/echosystemname/esbi)
