React - Ben Newman - Facebook
---
Tidbits:
----
* It allows rewriting source code programmatically
* Uses AST-types for ES6 functionality (May no longer be needed with latest Esprima/Parser API)
* Preserves comments
* Only updates parts that are changed ( preserves formatting )

<div class="fragment"/>
Use:
---
* Builder for all of the different statment/expression types.  Will likely need to visit recursively.
* If you're missing a param, will alert you with name.
* Visitor Pattern is the easiest way to use.
