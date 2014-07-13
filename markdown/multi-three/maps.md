### The One Where Phoebe Forgets Something
```
   var wm = new WeakMap();
   var m = new Map();
   var s = new Set();
   (function() { 
     var c = {'not':'me'};      
     m.set(c,{'o':'k'});
     wm.set(c,{'o':'k'});
     s.set(c);
     console.log(wm.get(c));
   }
   )()
   
   wm.has(m.keys().next().value); 
   s.has(m.keys().next().value);
   m = undefined;
   s = undefined;
   //after next gc wm.size (if it existed) would be 0

  //ES6 Spec..an ECMAScript implementation must not provide any means to observe a key of a 
  //WeakMap that does not require the observer to present the observed key.
   
   
```
Note:Hey you.  Go line by line.
Make sure to go into how yield pauses execution until the next time data is needed.
