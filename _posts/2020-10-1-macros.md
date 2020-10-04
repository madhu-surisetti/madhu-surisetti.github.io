---
layout: post
title: macros
publish: t
type: essay
start: oct 1, 2020
last: oct 3, 2020
---

## how do macros help you
i use macros for templates or as a substitute for functions when i couldn't afford calling one.
macros aid in writing embedded languages on top of lisp which is economical because you save yourself a lot of work adding only features you need and keep the rest of lisp.
if something has to be useful, it's obvious that you have to _use_ it. often.
if it's only useful once in a blue moon, it's usually not worth the effort.
from what i hear, smart hackers use macros all the time.
so i'm going to take a chance and try to understand macros.
that's what this essay is going to be about.
figuring out how to use macros.

## what macros represent
clearly macros are a tool for abstraction.
but abstract what?
functions abstract procedures
(in lisp functions also abstract data).
closures abstract procedures with state.
loops abstract repetition.
conditionals abstract choice.
what do macros abstract?
macros abstract what the language doesn't.
macros help create a direct mapping between your ideas and code.
macros let lisp evolve.

## but how can it do so much
in lisp, programs are lists.
macros shine at transforming lists.
writing macro definitions is basically, figuring out where the car of each cons cell goes.
if you want to find out how macros do so much, you need to know what kind of list-transformations macro can do.
### reference
macros can do destructuring-bind, which is binding values and variables based on position.
after the macro call, all the arguments including body are lists.
which means you can use all the subroutines in lisp that take lists as arguments.
if you can treat code as data, then you pass that data as argument to subroutines at compile time.
imagine the countless data structures a list can emulate and the contents being the source code.

## why not just use functions
it's inelegant to use macros where functions would do.
this is where the source of confusion is => (what macros can do) ⋂ (what functions can do).
if you want to resolve this, you should look at _what macros can only do_.
macros can generate programs based on the arguments.
setf is a general purpose operator that generates code from its arguments.
the arguments to a functions are evaluated before they even get to functions, where as the arguments to macros are lists.
when posssible, you can shift computation to compile time with macros.
you can observe that, while function calls are rarely longer than a line, whole programs are written inside macro calls.
the general rule is functions are computation oriented and macros are abstraction oriented.
which means if you can express your intention through computation, you should use subroutines.
if you can't, using macros is the path.

## using macros
