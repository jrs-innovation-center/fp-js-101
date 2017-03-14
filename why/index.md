# Why learn Functional JavaScript?

> Functional programming (often abbreviated FP) is the process of building software by composing pure functions, avoiding shared state, mutable data, and side-effects. Functional programming is declarative rather than imperative, and application state flows through pure functions. Contrast with object oriented programming, where application state is usually shared and colocated with methods in objects.

> Functional programming is a programming paradigm, meaning that it is a way of thinking about software construction based on some fundamental, defining principles (listed above). Other examples of programming paradigms include object oriented programming and procedural programming.

> Eric Elliot - https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0#.oj4ks43pv

* Pure functions
* Function composition
* Avoid shared state
* Avoid mutating state
* Avoid side effects

> Shared Mutating State is the root of all evil

## What is a pure function?'

Pure functions are function when given the same input will always return
the same output?

## What is function composition?

Functional composition is taking multiple functions and combining them together
to create a more complex function.

> f(a, b, c) === d => a(b(c(d)))

```
TODO: Code Pen Example
```


## What is shared state?

> Shared state is any variable, object, or memory space that exists in a shared scope, or as the property of an object being passed between scopes. A shared scope can include global scope or closure scopes. Often, in object oriented programming, objects are shared between scopes by adding properties to other objects.

> The problem with shared state is that in order to understand the effects of a function, you have to know the entire history of every shared variable that the function uses or affects.

> Remove function call timing dependency, and you eliminate an entire class of potential bugs.

Understanding how your program processes state and removing the concept of time
out of your debugging process, makes finding bugs quick and easy.

When you introduce time into your state, then bugs can be very hard to find and reproduce.

## What is mutating state?

Immutability is simply return a new version of an existing value, instead of a
modified version of the same value. By treating structures like arrays and objects
as immutable data, your state can not mutate. Strings and Numbers are immutable by default. Instead of changing the same value, return a new value.

```
const a = [1,2,3]
const b = a.map(v => v + 1)
#> b === [2,3,4]
#> a === [1,2,3]
```

a will always be [1,2,3]
b will be a new array with [2,3,4]

## What is side effects?

Side Effects is anything outside of your program. Databases, Network, UI, Logging to console, calling other functions with side effects.

Basically, your application has to access these things to be of any value, the focus is to keep the access of side effects and the edges of your application and not inside the internals of the application.

[index](../)
