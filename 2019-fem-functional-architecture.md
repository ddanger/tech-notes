# Functional Architecture in JavaScript

Slides and maybe code in future [here](https://docs.google.com/presentation/d/1L5gxYQz2hyzbVJk5tkyNdDidf_cg4I1BlIGd_Y9jblU)

This is what I got out of it:
- FP with strong types is very different from doing it in JS
- In JS we create "types" like Either, Task, etc. which we can use to enable chaining and other things
- Also a nice idea to create domain types like this instead of just random data all over the place:
```
const User = ({firstName, lastName}) => ({
  firstName,
  lastName
})

const person = User({firstName: Bob, lastName: Jones})
```
- He doesn't seem to think it's worth the effort to go the TypeScript route in JS. It seems he thinks it's too much work (and hacking) for too little benefit. He seems to prefer his style of doing it without strong types
- This stuff can be really confusing and a total mindset change. Would need lots of buy-in to start on it.
- I thought this paraphrase of something he said was insightful about the value of functional programming:
>People obsess about their folder structure and what to put into various files.
>Usually I've found this is because they aren't writing their things in a portable way.
>We can just throw everything into a file because it's all totally portable.
>The functions can be copied/pasted anywhere.
>Typically we start with everything in the same file and copy/paste it into multiple files/folders as it becomes unmanagable

His book versions
https://mostly-adequate.gitbooks.io/mostly-adequate-guide/ and https://drboolean.gitbooks.io/mostly-adequate-guide-old/

Exercises
https://codepen.io/drboolean/pen/MpKpee

Exercises
https://codepen.io/drboolean/pen/qeqpgB

Exercises
https://codepen.io/drboolean/pen/NQKByP

FP Slack
https://functionalprogramming.slack.com

Strangest Tutorial Ever
https://www.youtube.com/watch?v=RkDtMeZXMTA

Oh Composable World (React Rally talk) Contramapping components example
https://youtu.be/SfWR3dKnFIo?t=1226

Source code for immutable-ext
https://github.com/DrBoolean/immutable-ext/blob/master/index.js
