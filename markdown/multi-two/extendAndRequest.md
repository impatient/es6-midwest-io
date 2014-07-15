### Continued
```
class JSONResolver extends HttpResolver { //extends
  getData() {
   return JSON.parse(super.getData());
  }
}


var url = 'http://taginfo.openstreetmap.org/api/4/search/by_keyword?query=fire&page=1&rp=10',
  method = 'get';   

//thanks to openstreetmap for the easily accessible cors api.
var act = new HttpResolver({url, method});  
var act2 = new JSONResolver({url, method});  
 
act.promise.then((data) => console.log(typeof data));
act2.promise.then((data) => console.log(typeof data));
```