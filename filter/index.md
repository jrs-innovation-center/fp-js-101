# Filter

A filter function takes a list of items and transforms it into another list
of the same items.

```
const reduce = (fn, defaultValue, list) => {
  let result = defaultValue
  for (var i = 0; i < list.length; i++) {
    result = fn(result, list[i])
  }  
  return result
}

const filter = (fn, list) =>
  reduce((acc, value) => fn(value) ? [...acc, value] : acc , [], list)

console.log(filter(v => v % 2 === 0, [1,2,3,4,5,6]))
```

<iframe width="800" height="500" frameborder="0" src="http://pythontutor.com/iframe-embed.html#code=const%20reduce%20%3D%20%28fn,%20defaultValue,%20list%29%20%3D%3E%20%7B%0A%20%20let%20result%20%3D%20defaultValue%0A%20%20for%20%28var%20i%20%3D%200%3B%20i%20%3C%20list.length%3B%20i%2B%2B%29%20%7B%0A%20%20%20%20result%20%3D%20fn%28result,%20list%5Bi%5D%29%0A%20%20%7D%20%20%0A%20%20return%20result%0A%7D%0A%0Aconst%20filter%20%3D%20%28fn,%20list%29%20%3D%3E%0A%20%20reduce%28%28acc,%20value%29%20%3D%3E%20fn%28value%29%20%3F%20%5B...acc,%20value%5D%20%3A%20acc%20,%20%5B%5D,%20list%29%0A%0Aconsole.log%28filter%28v%20%3D%3E%20v%20%25%202%20%3D%3D%3D%200,%20%5B1,2,3,4,5,6%5D%29%29&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=56&heapPrimitives=false&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>


[Index](../)
