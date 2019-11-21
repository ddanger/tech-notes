# Domain Modeling Made Functional

### Functional DDD doesn’t have: entities, value-something… (get the list from him)
- Types as executable documentation
- Use the language as the documentation
- Four Candles Sketch
  - assumptions
  - communication

- About Project Management: More important to go in the right direction than go fast

### Projects fail because:
- they're using PHP
- no j/k because they are doing the wrong thing

### Ideal Software Process
- Build shared mental model
- Have frequent feedback
- Value effectiveness over speed

<blockquote>The design is the code, and the code is the design</blockquote>

- Business events initiate business workflows
- Business events trigger commands which initiate business workflows which generate lists of events
- Event driven pipeline model as opposed to a "Layered" approach.

- Problem space is the real world
- Solution space is the code.
- Must minimize the solution space. Don't model stuff that doesn't matter
- "Every program attempts to expand until it can read mail." Just. Don't!

- Customer:
  - Marketing - someone with an email address
  - Finance - someone who owes us money

## Domain Modeling
- Not OO Modeling
- Not DB Modeling
- Domain modeling comes after Event Storming. Event Storming is a mob exercise.
- Domain modeling results in something like:
- TicTacToe domain
```
workflow NewGame =
  triggered by: NewGameRequest
  Input: Player names x 2
  Output: NewBoard
  output event: NewGameStarted


workflow PlayerMoves =
  triggered by: MoveRequest
  Input:  Location
  Output: Updated Board AND Disposition
  output event: PlayerMoved

data Disposition =
   Won (with Player)
   OR Drawn
   OR InPlay (with next Player)

data Location = Row AND Column

data Row = Top OR Middle OR Bottom
data Column = Left OR Center OR Right

data Board = Cell list
data Cell = Row AND Column AND optional Mark
data Mark = Cross OR Nought
data Player = Name AND Mark
```
## Intro to F#

## Functional Programming
- Functions like legos, Composition of functions (immutability is required)
- Ultimately you can build till you get: HTTP Request -> HTTP Response
- Types are not functions, they are just a name for a set of things
- A type could be a set of functions
- ~Algebraic~ Composable Type system - new types are created from smaller ones with AND and OR
- type Snack = Apple of AppleVariety | Banana of BananaVariety

What's the problem with this type:

type Contact = {
  FirstName: string
  MiddleInitial: string
  LastName: string
  EmailAddress: string
  IsEmailVerified: bool
}

- IsEmailVerified is a problem
- Booleans are red flag, we should have.
- It's a choice. Booleans don't convey that well.
- Business Rules are what we're trying to implement.
- We want to implement them in code in the type system, not in a comment or tribal knowledge
```
type VerifiedEmail = VerifiedEmail of EmailAddress
type VerificationService =
  (EmailAddress * VerificationHash) -> VerifiedEmail option
type EmailContactInfo =
  | Unverified of EmailAddress
  | Verified of VerifiedEmail
```
<blockquote>"Making illegal states unrepresentable"</blockquote>
Why? So you don't have to write code or tests to check it.

## Functional Architecture
- Bounded Contexts are software building blocks (modules, containers, microservice)
- Modular code enabled you to easily switch between monolith, SOA and microservices
- Not a traditioinal layered model (it's going out of fashion)
  - problem is, if you change a workflow, you havae to touch every layer
  - code that changes together should live together
  - vertical slices are the new hotness
  - no service, application, domain, database ... it's just a function with input/output
  - workflows change independently
  - DRY can be overdone, I'd rather repeat myself than have my change cause breakage
  - "onion architecture" (ports and adapters, clean architecture) is how to implement the new hotness
### Frontend
- MVU Model, View, Update (Elm, React, Vue, etc)

General
- He believes in simplified DDD without a lot of the jargon (entity,repository, specification)
- Booleans are bad, use state machines with Types.
- Exceptions are bad. Use pipeline of code through functions with error flows on separate track
- Layered architecture is bad. Use onion architecture instead.
- Separating out the core domain logic is kind of like an application store a la redux/vuex
- If in the JVM, he prefers Kotlin over Scala over Java
