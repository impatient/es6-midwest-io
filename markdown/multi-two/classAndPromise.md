The One with the Long Distance Relationship
```
class HttpResolver { //class
  constructor({url, method, data}) {
    this._xmlHttpRequest = new XMLHttpRequest();    
    this._promise = new Promise(this.resolve.bind(this)); //context is important here es5
    this._xmlHttpRequest.open(method, url);
    this._xmlHttpRequest.send(data); 
  }
  getData() {
   	return this._xmlHttpRequest.responseText;
  }
  resolve(resolve,reject) {
    
    this._xmlHttpRequest.onreadystatechange = () => { 
      if(this._xmlHttpRequest.readyState==4 && this._xmlHttpRequest.status==200) {
          resolve(this.getData());
      }
    }
    this._xmlHttpRequest.ontimeout = () => { throw new Error('timeout'); }
  }
  get promise() { return this._promise; } //get modifier (Use .promise instead of .promise() es5
}
```