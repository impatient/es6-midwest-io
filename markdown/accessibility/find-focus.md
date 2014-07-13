####Find Focusable Elements

var isFocusable = (elem) => elem &&  elem.tabIndex >= 0;
var timeFunction = function(toTime) { return () => { 
  console.time('ListFocus');
  var result = toTime.call(this,...Array.from(arguments));
  console.timeEnd('ListFocus'); 
  return result;  };
}; 

class ParseFocusable {
 
  constructor({domElement, filter=isFocusable, timeFocus=false}) {
    this.domElement = domElement;
    this.isFocusable = filter;
    if(timeFocus === true) {
     this.focusArray = timeFunction.bind(this)(this.focusArray); 
    }
   
  }
 
  *focii(domElement, ignoreSelf) {
    //console.log('inspecting',domElement);
    if(!domElement) {return; }
	var isHidden = this.isHidden(domElement);
  	if(!ignoreSelf && this.isFocusable(domElement) && !isHidden) {
      yield domElement
    }
    if(!isHidden) {
    	yield *this.focii(domElement.firstElementChild)
    }

    if(!ignoreSelf){
     yield *this.focii(domElement.nextElementSibling);
    }

  }
  
  isHidden(domElement) {
    if(!domElement) {return true; }
    return domElement.offsetWidth <= 0 && domElement.offsetWidth <= 0 || domElement.getAttribute('aria-hidden') === "true";
  }

  focusArray() {
	return [for(n of this.focii(this.domElement,true)) n];
  }

}

console.clear(); 
var allElements = new ParseFocusable({domElement:document.body,timeFocus:true}).focusArray();
console.log(allElements);