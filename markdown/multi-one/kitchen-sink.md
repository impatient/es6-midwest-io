### The One With the Kitchen Sink
```
//arrow + destructuring + default params
var fibNext=({last=0,current})=>{ return last + current};
var gen = function *(...two ) { //generator + rest params
  var [last,current] = two;  //destructuring
  var next = fibNext({last,current}); //shorthand object syntax
  while(next < 1000) {
    next = fibNext({last,current});
    [last, current] = [current,next]; //destructuring
    yield next; //yield keyword (for generators)
  }
}
for(let z of gen(0,1)) { //generator + let
  var q = [ for (n of gen(...[0,1])) if (n=== z) n ]  //iterators + array comprehension + spread operator
  console.log(````Runtime complexity ${q}````); //string templating
}

export gen //modules
```
Note: Test
  