# Reduce

Reduce is the core building block of pure functional methods for data structures.
(array and object)

A reduce function takes a collection and an initial value and iterates over
every value in the collection and applies a `reducer` function, once complete
you have a new value.

## Structure

### reduce function

* reducer function
* initial value
* collection

### reducer function

* previous result or accumalator
* value

## Example

The reduce function can take a list of numbers and return a sum of those numbers.

```
function sumReducer (acc, value) {
  return acc + value
}

function reduce (reducer, initialValue, list) {
  let result = initialValue
  for (let i = 0; i < list.length; i++) {
    result = reducer(result, list[i])
  }
  return result
}

function sum (list) {
  return reduce (sumReducer, 0, list)
}
```

## Demo

<iframe width="800" height="500" frameborder="0" src="http://pythontutor.com/iframe-embed.html#code=function%20reduce%20%28reducer,%20initial,%20list%29%20%7B%0A%20%20let%20result%20%3D%20initial%0A%20%20list.forEach%28function%20%28value%29%20%7B%0A%20%20%20%20result%20%3D%20reducer%28result,%20value%29%0A%20%20%7D%29%0A%20%20return%20result%0A%7D%0A%0Afunction%20add%20%28a,%20b%29%20%7B%0A%20%20return%20a%20%2B%20b%0A%7D%0A%0Alet%20total%20%3D%20reduce%28add,%200,%20%5B1,2,3%5D%29&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=0&heapPrimitives=false&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

## Exercises

### Exercise 1

Re-key the code above and then use the sum function to get the sum of the following
list of numbers:

* 1,2,3
* 42, 84, 168
* 21, 33, 99, 299

---

<p data-height="265" data-theme-id="0" data-slug-hash="pRKWYa" data-default-tab="result" data-user="twilson63" data-embed-version="2" data-pen-title="reduce exercises" class="codepen">See the Pen <a href="http://codepen.io/twilson63/pen/pRKWYa/">reduce exercises</a> by Tom Wilson (<a href="http://codepen.io/twilson63">@twilson63</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

---

### Exercise 2

Create a map function using the reduce function.

A map function takes a list of values and applies a mapper function on each value
returning a new list of values.

#### Demo

<iframe width="800" height="500" frameborder="0" src="http://pythontutor.com/iframe-embed.html#code=function%20reduce%20%28reducer,%20initial,%20list%29%20%7B%0A%20%20let%20result%20%3D%20initial%0A%20%20list.forEach%28function%20%28value%29%20%7B%0A%20%20%20%20result%20%3D%20reducer%28result,%20value%29%0A%20%20%7D%29%0A%20%20return%20result%0A%7D%0A%0Afunction%20append%20%28value,%20list%29%20%7B%20return%20list.concat%28%5Bvalue%5D%29%20%7D%0A%0Afunction%20map%20%28fn,%20list%29%20%7B%0A%20%20return%20reduce%28%28acc,%20value%29%20%3D%3E%20append%28fn%28value%29,%20acc%29,%20%5B%5D,%20list%29%0A%7D%0A%0Alet%20doubleNumbers%20%3D%20map%28n%20%3D%3E%20n%20*%202,%20%5B1,2,3,4,5%5D%29&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=0&heapPrimitives=false&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

#### Example

```
const double = v => v * 2
const result = map(double, [1,2,3])
#> [2,4,6]
```

A map function would take the following arguments:

* mapper - the mapper function that takes 1 argument and returns a new value
* list - the array of values that you want to iterate over.


<p data-height="265" data-theme-id="0" data-slug-hash="XpYzro" data-default-tab="js,result" data-user="twilson63" data-embed-version="2" data-pen-title="Create your own Map Function" class="codepen">See the Pen <a href="http://codepen.io/twilson63/pen/XpYzro/">Create your own Map Function</a> by Tom Wilson (<a href="http://codepen.io/twilson63">@twilson63</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

---

### Exercise 3

Create a filter function using the reduce function

A filter function takes a list of values and applies a predicate function to each value returning a list of values that only resulted in true.

#### Demo

<iframe width="800" height="500" frameborder="0" src="http://pythontutor.com/iframe-embed.html#code=function%20reduce%20%28reducer,%20initial,%20list%29%20%7B%0A%20%20let%20result%20%3D%20initial%0A%20%20list.forEach%28function%20%28value%29%20%7B%0A%20%20%20%20result%20%3D%20reducer%28result,%20value%29%0A%20%20%7D%29%0A%20%20return%20result%0A%7D%0A%0Afunction%20append%20%28value,%20list%29%20%7B%20return%20list.concat%28%5Bvalue%5D%29%20%7D%0A%0Afunction%20filter%20%28fn,%20list%29%20%7B%0A%20%20return%20reduce%28%28acc,%20value%29%20%3D%3E%20fn%28value%29%20%3F%20append%28value,%20acc%29%20%3A%20acc,%20%5B%5D,%20list%29%0A%7D%0A%0Alet%20odd%20%3D%20filter%28n%20%3D%3E%20n%20%25%202%20!%3D%3D%200,%20%5B1,2,3,4,5%5D%29&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=0&heapPrimitives=false&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

---

### Exercise 4

Create a reject function using the reduce function

A reject function takes a list of values and applies a predicate function to each value and returns a list of values that only returned a false in the predicate function

---

### Exercise 5

Create a take function using the reduce function

A take function takes a number of values to return from the start position and a
list of values. It returns the first x values from the list.

---

### Exercise 6

Create a contains function, that returns true if a value is in a list.

### Exercise 7

Create a times function

### Exercise 8

Create an append function

** Fork the following pen to create and test your exercises

http://codepen.io/twilson63/pen/LxrOPP?editors=0010

[Index](../)
