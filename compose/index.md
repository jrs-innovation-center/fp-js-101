# What is Functional Composition

In functional programming you want simple functions that do one thing really well. Taking these functions and combining them via chaining or point-free can become a challenge to keep straight the more complex your functionality gets.

If you have a function f(v) and a function g(v) then with composition you can call f(g(v)), which will take the result of g(v) and call f returning a composed result.

```
f(g(v)) === compose(f,g)(v)
```

# Understanding the Compose Function

<iframe width="800" height="600" frameborder="0" src="http://pythontutor.com/iframe-embed.html#code=const%20add%20%3D%20curry2%28%28a,b%29%20%3D%3E%20a%20%2B%20b%29%0Aconst%20tap%20%3D%20v%20%3D%3E%20%7B%0A%20%20console.log%28v%29%0A%20%20return%20v%0A%7D%0A%0Alet%20total%20%3D%20compose%28%0A%20%20add%2810%29,%0A%20%20tap,%0A%20%20add%285%29,%0A%20%20tap,%0A%20%20add%2822%29%0A%29%285%29%0A%0A%0A%0Afunction%20curry2%28fn%29%20%7B%20%0A%20%20return%20%28a%20,b%29%20%3D%3E%20!b%20%3F%20b%20%3D%3E%20fn%28a,b%29%20%3A%20fn%28a,b%29%20%0A%7D%0A%0Afunction%20compose%20%28...fns%29%20%7B%0A%20%20return%20v%20%3D%3E%20reduce%28%28a,%20v%29%20%3D%3E%20v%28a%29,%20v,%20fns.reverse%28%29%29%0A%7D%0A%0Afunction%20reduce%20%28reducer,%20initial,%20list%29%20%7B%0A%20%20let%20result%20%3D%20initial%0A%20%20list.forEach%28v%20%3D%3E%20result%20%3D%20reducer%28result,%20v%29%29%0A%20%20return%20result%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=0&heapPrimitives=false&origin=opt-frontend.js&py=js&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>


[Index](../)
