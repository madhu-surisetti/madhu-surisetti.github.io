---
layout: page
title: CommonLisp Phrasal Reference
permalink: /clpr/
publish: nil
type: list
---

I Love Lisp.
I love it because it lets me stay in my head.
Before lisp, the idea of enjoying programming sounded kind of phony to me.
I mean I enjoyed the problem solving part of programming.
This is the part where I get to stay in my head and fantasize about cool solutions.
But when it gets to implementing the solution, it's a pain.
I used to get lost in the details, the small stuff of syntax.
There's a big translation overhead from my thoughts to the program.
I couldn't say what I wanted how I wanted to.
I hated programming.
But I still loved solving problems.

And by luck, somehow I came across lisp and I loved it.
It lets me tell the computer exactly what I wanted to say and how I wanted to say it.
It lets me cut through the syntactic obligation and stay in my head.

But to make my experience even better, I am creating this CommonLisp Phrasal Reference.
I don't know if this kind of references exists, but this is the way I think.
This phrasal reference is something that bridges the very very small gap that exists in CommonLisp and Plain English.


### Get the first element out of a list while removing it ###
`(pop *list*)`

### Get the first element out of a list without removing it ###
```lisp
(car *list*)
```

### Load the file into a string ###
```lisp
(uiop:read-file-string "file.txt")
```

