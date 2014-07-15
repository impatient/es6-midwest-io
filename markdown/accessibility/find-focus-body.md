####Find Focusable Elements
```
class ParseFocusable {
  constructor({domElement, filter=isFocusable, timeFocus=false}) {
    this.domElement = domElement;
    this.isFocusable = filter;
    this.focusArray = timeFunction.bind(this)(this.focusArray); 
    
  } 
  *focii(domElement, ignoreSelf) {
    var isHidden = isHidden(domElement);
    if(!ignoreSelf && this.isFocusable(domElement) && !isHidden) {
      yield domElement
    }    
    if(!isHidden) {//if not hidden traverse
      yield *this.focii(domElement.firstElementChild)
    }    
    if(!ignoreSelf){//if not initial object, get siblings
      yield *this.focii(domElement.nextElementSibling);
    }
  }
  focusArray() {
	return [for(n of this.focii(this.domElement,true)) n];
  }

}

console.clear(); 
var allElements = new ParseFocusable({domElement:document.body,timeFocus:true}).focusArray();
console.log(allElements);
```