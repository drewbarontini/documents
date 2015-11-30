CoffeeScript Module
===================

```coffeescript
### 
  Set up the namespace, if it doesn't already exist to make
  the object available globally.
###
@App ?= {}
 
# CoffeeScript shortcut for a self-invoking anonymous function
App = do ->
 
  privateVar = ''
  
  privateMethod = ->
 
  publicMethod: privateMethod
 
$ -> App.publicMethod()
```
