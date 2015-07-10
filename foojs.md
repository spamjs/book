# foo.js

##is(type,obj)

| Argument | Type | Valid Values |
| -- | -- | -- |
| type | string | Array,Function,String,Object,Boolean,Number,Undefined,Null |
| obj | mixed | ANY |



To check the type of javascript Object.
```javascript
    window.is("Function", myObj);
    //will return true or false
    window.is("Array", myObj);
    window.is("String", myObj);
```
##is.Array(obj)
##is.Number(obj)
##is.Function(obj)
##is.Null(obj)
##is.Undefined(obj)
##is.Value(obj)
 Returns TRUE if obj is neither _null_ nor _undefined_
##is.Empty(obj)
 Returns TRUE if obj is _null_, _undefined_,_false_,_0_,EMPTY_ARRAY, EMPTY_OBJECT or EMPTY_STRING


