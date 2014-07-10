Is Roughly Equivalent To(ES5)
---
```
   var sum = function(a,b) { 
    return a+b;
   }

```
<div class="fragment"/>
Is Equivalent To:
---
```
   var sum = function(a,b) { 
       return a+b;
   }.bind(this);
```

