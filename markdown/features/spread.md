Spread Operator
---
```
var a = [1,2,3];

var sum = function(one,two, three) { 
  return Array.from(arguments).
  reduce( 
    (memo, b) => { return b + memo; },0
  );
  
};
      
 
console.log(sum(...a)); //6
```