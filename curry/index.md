# Curry (auto curry)

Enables you to call a function with partial arguments and it will return a function
seeking the remaining arguments.

```
const curry = (fn , list = []) => (...args) =>
  (a => a.length === fn.length ? fn(...a) : curry(fn, a))([...list, ...args])

function add (a, b) {
  return a + b
}

const add10 = curry(add)(10)

console.log(add10(5))
```

Result will be 15

----

Why use curry? Curry, can convert functions that take multiple arguments into
functions that are unary, which enables you to compose several components to
create more complex components


```
const {compose, map, filter, pluck, propEq, join} = R
const docs = [
  {doc: {name: {first: 'Mickey', last: 'Mouse'}, type: 'patient'}},
  {doc: {name: {first: 'Donald', last: 'Donald'}, type: 'doctor'}},
  {doc: {name: {first: 'Minnie', last: 'Minnie'}, type: 'patient'}}
]

const patientsOnly = filter(propEq('type', 'patient'))
const toLI = map(doc => `<li>${doc.name.first} ${doc.name.last}</li>`)

document.getElementById('list').innerHTML = compose(
   join(''),
   toLI,
   patientsOnly,
   pluck('doc')
)(docs)

```


[Index](../)
