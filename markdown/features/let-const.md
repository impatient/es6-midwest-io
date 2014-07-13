### Let and Const 
```
   const always= 'always';
   if(1 === 1) {
      let x = 2;
   }
   always = 'not-always'; //traceur lets you do this
   console.log(x);  //reference error undefined
   

```
####Caveat, under experimental in traceur.  
Note: This is where a linter would be better than this behavior.
 
 