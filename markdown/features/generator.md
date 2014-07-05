Generator
---
```

var generator = function*(initial) {
  var individual = initial.split('');
  var i =0;
  while( i< individual.length -1)
  {    
	yield individual[i];
    ++i;
  }
  return individual[i];

};

var a = generator('testMe');

console.log(a.next()) //Object {value: "e", done: false} 
console.log(a.next()) //Object {value: "s", done: false} 
console.log(a.next()) //Object {value: "t", done: false} 
console.log(a.next()) //Object {value: "M", done: false} 
console.log(a.next()) //Object {value: "e", done: true} 

```