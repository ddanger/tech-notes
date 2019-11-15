# Hardcore Functional Programming in JavaScript

Slides [here](https://docs.google.com/presentation/d/1nj5xmsHeJh-6RdjLs1190Hwl8smclvFLePqPCTVsrYw/edit#slide=id.g338d117be_040)

## Terminology
- total function: will always return a value for every input (not undefined, null, throw, etc.)

Throwing is bad, returning promises is good (reject instead of throw)

## Currying
Example with 2 args
`const curry = f => x => y => f(x, y)`

Exercises:
https://codepen.io/drboolean/pen/OJJOQMx

## Compose
Example with 2 functions
`const compose = (f, g) => x => (f(g(x)))`

With those two you can pipe data through small functions to get at your result

Functions are composable/testable

Exercises
https://codepen.io/drboolean/pen/zYYPmZO

## Functors
Something with a `map` method.
"Box" Example (actually a functor _and_ a monad):
```
const Box = x =>
({
  map: f => Box(f(x)),
  fold: f => f(x),
  toString: () => `Box(${x})`
})
```

Exercises
https://codepen.io/drboolean/pen/poodxOm

## Monads

Exercises
https://codepen.io/drboolean/pen/xgoeWR

## Task
Like a Promise but it's lazy. Does nothing 'till you "fork" it to make it run.

Exercises
https://codepen.io/drboolean/pen/Mparbp

## Debugging
He wrote an article on it
https://medium.com/@drboolean/debugging-functional-7deb4688a08c

## Introducing New Teams
His advice is to start with "Either" and "Task". That causes everything else to come in.
