Continued
```
class JSONResolver extends HttpResolver { //extends
  getData() {
   return JSON.parse(super.getData());
  }
}

var request = (options) => { //arrow function
  
  var {url, method, data, Resolver} = options;
  return new Resolver({url,method,data});//shorthand object creation

};

//thanks to openstreetmap for the easily accessible cors api.
var act = request({ 
   url: 'http://taginfo.openstreetmap.org/api/4/search/by_keyword?query=fire&page=1&rp=10',  
   method:'get', Resolver: HttpResolver });  
var act2 = request({ 
   url:'http://taginfo.openstreetmap.org/api/4/search/by_keyword?query=fire&page=1&rp=10', 
   method:'get', Resolver: JSONResolver });  
 
act.promise.then((data) => console.log(typeof data));
act2.promise.then((data) => console.log(typeof data));
```