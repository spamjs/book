# foo.js

##is
###is.Array(obj)
###is.Number(obj)
###is.Function(obj)
###is.Null(obj)
###is.Undefined(obj)
###is.Value(obj)
 Returns TRUE if obj is neither _null_ nor _undefined_
###is.Empty(obj)
 Returns TRUE if obj is _null_, _undefined_,_false_,_0_,EMPTY_ARRAY, EMPTY_OBJECT or EMPTY_STRING

##to
###to.List
```javascript
to.List("a,b,c");
//["a","b","c"]
to.List(["a",,"b","c"]);
////["a","b","c"]
to.List(["a",,"b",null]);
////["a","b"]
```


##JSONPath(sourceObj, defaultValue)

```javascript
var jsonpath = new JSONPath("a.b.c");
var map = {a : { b : c : { d : "D" }}};
var map2 = {a : { b : c : { e : "D" }}};

jsonpath.load(map);
// { d : "D" }

jsonpath.load(map2);
// undefined

jsonpath.load(map2,"OK");
// "OK"
```

##Global Functions
###window.debounce(func, delay)
it limits the rate at which a function can fire. A quick example:  you have a resize listener on the window which does some element dimension calculations and (possibly)  repositions a few elements.
[Source](https://davidwalsh.name/javascript-debounce-function)

###window.getUUID()
Generates universal unique id

###window.until(callback,condition,delay)
Executes a fucntion repeatedly till condition function returns true



