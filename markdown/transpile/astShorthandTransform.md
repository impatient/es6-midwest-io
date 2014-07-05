Transform
---
```
   var Shorthand = Visitor.extend( {
      visitObjectExpression: function(objectExpression) {
        var newProperties = objectExpression.properties.map(function(prop) {
          return b.property(
            prop.kind,
            prop.key,
            this.visit(prop.value),
            prop.method,
            false);
        }.bind(this));
   
        return b.objectExpression(newProperties);
   
      }
   
   });
   
    new Shorthand().visit(ast);
   
   var output = recast.print(ast).code;

```