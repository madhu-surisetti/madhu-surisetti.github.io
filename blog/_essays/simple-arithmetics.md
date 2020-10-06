---
layout: essay
title: spoj - simple arithmetics
start: oct 5, 2020
last: oct 6, 2020
---

[simple-arithmetic](https://www.spoj.com/problems/ARITH/)
the most obvious way would be to write separate code for each of the operations.
instead, let's do it the lisp way.
everything's the same until it's not.

printing multiplication is the problem.
usually, the right data structures make the problem simpler.
i'm thinking table.

now you choose a datum.
it can't be on the left side beacuse there's nothing to hang on to.
let it be on the right side.
we measure the padding from the right side.
this is simple to find.
what's not simple to find is the padding on the left side.
this is where choosing the datum on the right side helps.
there must be a left boundary from which left-padding is measured.
we can find out where the left-boundary is by the longest of (number + left-padding).
that's the distance between left and right boundaries.
the rest should be easy.