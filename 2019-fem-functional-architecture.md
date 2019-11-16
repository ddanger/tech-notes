# Functional Architecture in JavaScript

Slides and maybe code in future [here](https://docs.google.com/presentation/d/1L5gxYQz2hyzbVJk5tkyNdDidf_cg4I1BlIGd_Y9jblU)

- Monads don't compose so normalizing effect types throughout app is probably something you want to do

// Semigroup

- closed: if you union or intersect, you'll get same type back
- associative:
closed + associative = parallel

I'm already mostly lost at this point (and honestly not interested in the low level here unless there was some way I could work on a team of people who get this stuff, but I don't see that happening)

Exercises
https://codepen.io/drboolean/pen/MpKpee

Exercises
https://codepen.io/drboolean/pen/qeqpgB

Exercises
https://codepen.io/drboolean/pen/NQKByP

Lenses
Lenses are built on functors but can do more.
The compose from left to right

People obsess about their folder structure and what to put into various files.
Usually I've found this is because they aren't writing their things in a portable way.
We can just throw everything into a file because it's all totally portable.
The functions can be copied/pasted anywhere.
