Let and Const - Experimental 
---
```
   const always= 'always';
   if(1 === 1) {
      let x = 2;
   }
   always = 'not-always'; //traceur lets you do this
   console.log(x);  //reference error undefined
   

```