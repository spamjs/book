# Module

Each module has its own events which gets triggered during its life cycle. By convention all the events are to be name with _underscore_ pre-suf-fix

```javascript
define({
    name : "myproject.app"
}).as(function(app){

    return {
        _instance_ : function(params){
            console.log("myproject.app instance is being created");
            //Note 'this' here referes to instance being created. So _instance_ can be used as contructor function.
        },
        _define_ = function(){
            console.log("myproject.app has been defined");
        },
        _ready_ = function(){
            console.log("Document is ready for DOM operations");
        }
    };
});
```
##Module Life Cycle Events
####\_instance_()

####\_define_()
####\_ready_()

##Module In-built Functions
####instance.parent()
return - parent Module it is extended from

####MODULE.path(path)
return - absolute path to file

####MODULE.instance()
return - new instance of that Module

####MODULE.is(type)
returns | TRUE of module extends the type

