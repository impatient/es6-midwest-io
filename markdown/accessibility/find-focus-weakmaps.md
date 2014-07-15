###Now with Weak Maps
```
class ParseFocusable {
  constructor() {
    this.forward = new WeakMap();
    this.reverse = new WeakMap();
  }

  buildTabOrder() {
    for(var [a,b] of sliding(this.focusArray())) {
      this.forward.set(a,b);
      this.reverse.set(b,a);
    }
  }

  next(domElement) {
    this.forward.get(domElement);   
  }
  previous(domElement) {
    this.reverse.get(domElement);
  }

}
```