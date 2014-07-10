### Spread Operator
```
var a = [1,2,3,4];

var sum = function(first,second, third,fourth) {
  console.log(fourth); //4
  return Array.from(arguments).
  reduce( 
    (a, b) => a+b
  );
  
};      
 
console.log(sum(...a)); //10
```