Code to Transform (Recast):
---
```
var recast = require('recast');
var Visitor = recast.Visitor;

var Arrow = Visitor.extend( {
   visitArrowFunctionExpression: function(arrow) {
     return b.callExpression(
       b.memberExpression(
         b.functionExpression(null, 
          arrow.params, 
          this.visit(fixBody(arrow.body)
          )
       ),
         b.identifier('bind'),false),
       [b.thisExpression()]);

   }

});

 new Arrow().visit(ast);
 
 var output = recast.print(ast).code;
 
 console.log(output);
 
 ```