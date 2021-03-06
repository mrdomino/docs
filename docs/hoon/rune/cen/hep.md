---
navhome: /docs/
next: true
sort: 2
title: %- "cenhep"
---

# `%- "cenhep"`

`[%cnhp p=hoon q=hoon]`: call a gate (function).

## Expands to

```
%~($ p q)
```

## Syntax

Regular: *2-fixed*.

Irregular: `(a)` is `$:a`; `(a b c d)` is `%-(a [b c d])`.

## Discussion

`%-` ("cenhep") is a function call; `p` is the function ([`gate`](../../bar/tis), 
`q` the argument. `%-` is a special case of [`%~` ("censig")](../sig), and a gate 
is a special case of a [door](../../bar/cab).

In a gate, the modified core has only one anonymous arm; in a
door it gets a full battery.  Intuitively, a gate defines one
algorithm it can compute upon its sample, `+6`. A door defines
many such algorithms.

In classical languages, doors correspond to groups of functions 
with the same argument list, or at least sharing a prefix.  In
Hoon, this shared sample is likely to be pulled into a door.

## Examples

```
~zod:dojo> =add-triple |=([a=@ b=@ c=@] :(add a b c))
~zod:dojo> (add-triple 1 2 3)
6
~zod:dojo> %-(add-triple [1 2 3])
6
```

