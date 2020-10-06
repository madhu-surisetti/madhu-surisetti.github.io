---
layout: page
title: lisp-love-freedom
start: sep 20, 2020
last: sep 20, 2020
---

What's special about lisp

## Language

 - Integers in Common Lisp can be almost arbitrarily large rather than being limited by the size of a machine word.
 - /= is not equals operator
 - Common Lisp implementation may place other limits on the size of number that can be represented. But these limits are going to be well beyond "astronomically" large numbers. For instance, the number of atoms in the universe is estimated to be less than 2^269; current Common Lisp implementations can easily handle numbers up to and beyond 2^262144.
 - :test => the boolean function used to compare
 - :key  => extract a key from the element and then use the key in comparison
 - :start, :end => so that you don't have to go through the whole list
 - :from-end t => start going through elements starting from the last element
 - :count => How many elements to remove
 - REDUCE is a surprisingly useful function--whenever you need to distill a sequence down to a single value, chances are you can write it with REDUCE, and it will often be quite a concise way to express what you want. For instance, to find the maximum value in a sequence of numbers, you can write (reduce #'max numbers). REDUCE also takes a full complement of keyword arguments (:key, :from-end, :start, and :end) and one unique to REDUCE (:initial-value). The latter specifies a value that's logically placed before the first element of the sequence (or after the last if you also specify a true :from-end argument). 
 - ELT is also a SETFable place.
 - sort, stable-sort, merage => destructive!!!

## Operators

### Sequences
 - count      => Number of times item appears in sequence
 - find       => Item or NIL
 - position   => Index into sequence or NIL
 - remove     => Sequence with instances of item removed
 - substitute => Sequence with instances of item replaced with new item
 - all of the above with IF appended
 - remove-duplicates
 - remove-if-not
 - copy-seq
 - reverse/nreverse
 - concatenate => like '+', except for sequences
 - merge => concatenate + sort
 - subseq => is a SETFable place
 - search => If you need to find a subsequence within a sequence
 - mismatch => To find where two sequences with a common prefix first diverge, you can use the MISMATCH function
 - every, some, notany, notevery
 - reduce => Maps over a single sequence, applying a two-argument function first to the first two elements of the sequence and then to the value returned by the function and subsequent elements of the sequence
 - maphash => iterate over the hash table
 - remhash => remove the hash
 - Destructive operators => NCONC, the recycling version of APPEND, and DELETE, DELETE-IF, DELETE-IF-NOT, and DELETE-DUPLICATES, the recycling versions of the REMOVE family of sequence functions

### Mapping
 - map => Like CONCATENATE and MERGE, MAP needs to be told what kind of sequence to create
   ```lisp
   (map 'vector #'+ #(1 2 3 4 5)
                    #(6 7 8 9 0)) ==> #(7 9 11 13 5)
   ```
 - map-into => MAP-INTO is like MAP except instead of producing a new sequence of a given type, it places the results into a sequence passed as the first argument
 - mapcar => the result is a new list(no type specifier needed like 'map')
 - maplist => MAPLIST is just like MAPCAR except instead of passing the elements of the list to the function, it passes the actual cons cells.13 Thus, the function has access not only to the value of each element of the list (via the CAR of the cons cell) but also to the rest of the list (via the CDR)
 - MAPCAN and MAPCON work like MAPCAR and MAPLIST except for the way they build up their result. While MAPCAR and MAPLIST build a completely new list to hold the results of the function calls, MAPCAN and MAPCON build their result by splicing together the results--which must be lists--as if by NCONC. Thus, each function invocation can provide any number of elements to be included in the result.14 MAPCAN, like MAPCAR, passes the elements of the list to the mapped function while MAPCON, like MAPLIST, passes the cons cells
 - 


### lists