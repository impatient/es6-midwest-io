###Setup
```
var isFocusable = (elem) => elem &&  elem.tabIndex >= 0;

var timeFunction = function(toTime) { return () => { 
  console.time('ListFocus');
  var result = toTime.call(this,...Array.from(arguments));
  console.timeEnd('ListFocus'); 
  return result;  };
}; 

isHidden(domElement) {
    if(!domElement) {return true; }
    return domElement.offsetWidth <= 0 && domElement.offsetWidth <= 0 ||
     domElement.getAttribute('aria-hidden') === "true";
  }
```

