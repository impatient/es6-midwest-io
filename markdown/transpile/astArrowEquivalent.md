ES5 Equivalent
---
```
     "type": "FunctionExpression",
                           "id": null,
                           "params": [
                               { "type": "Identifier", "name": "a" },
                               { "type": "Identifier", "name": "b" }
                           ],
                           "body": {
                               "type": "BlockStatement",
                               "body": [
                                   {
                                       "type": "ReturnStatement",
                                       "argument": {
                                           "type": "BinaryExpression",
                                           "operator": "+",
                                           "left": {
                                               "type": "Identifier",
                                               "name": "a"
                                           },
                                           "right": {
                                               "type": "Identifier",
                                               "name": "b"
                                           }
                                       }
                                   }
                               ]
                           },
                           "rest": null,
                           "generator": false,
                           "expression": false
                       }

```