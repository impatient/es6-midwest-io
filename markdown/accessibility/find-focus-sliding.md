###Sliding Generator
```
var sliding = function *(arr, numFields) {
  if(numFields <= 0) { numFields = 1; }
  var idx=0;
  
  while(idx + numFields < arr.length) {
    yield arr.slice(idx,idx+numFields);
    idx+=1;
  }
  
};

console.clear();

console.log( [for (x of sliding([1,2,3,4],2)) x]); //[1,2][2,3][3,4]

```
