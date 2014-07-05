Comprehensions
---
```
var a = [1,2,3]

//Array comprehensions
console.log([ for (x of a) x ]);

//Generator comprehension
var b = ( for (x of a) if(x %2) x );

console.log(b.next()) //Object {value: 1, done: false}
console.log(b.next()) //Object {value: 2, done: false}
console.log(b.next()) //Object {value: 3, done: false}
console.log(b.next()) //Object {value: undefined, done: true}
```