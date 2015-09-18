# View Module


A module having its own independant DOM presence referred as **View**

Its each instance has its own life cycle and predefined methods.

###Life Cycle
```javascript
define({
    name : "sidebar",
    extend : "spamjs.view"
}).as(function(sidebar){

    return {
        events : { //DOM events binder
            "click .mydiv .mybutton" : "function_name1",
            "click .my2div .my2button" : "function_name3"
        },
        _init_ : function(appConfig){//When View is Attached to DOM tree
            console.log("View is Intialized");
            this.$$.html("<div>Hello</div>");
        },
        _remove_ : function(){//When View is removed from DOM tree
            console.log("View is being removed from DOM");
        }
    };

});
```

###Properties

#####self.$$
jQuery DOM reference object for current view module instance
```javascript
self.$$.find(".myname").text("LNT");

```


###Methods

####self.add
adds child module to current module
```javascript
var CHILD_MODULE = module("child.module");

self.add(CHILD_MODULE.instance({
    id : "myID"
}));

```
**Note:-** One module can contain only one instance for particular id, if tried with duplicate it will remove previous instance and adds new one.

####self.addTo
Ideally used to initialize the top-most view which has no parent, and in absence of param will use body as container.
```javascript
MODULE.instance().addTo(jQuery("#mydiv"));
```

####self.remove
removes child module from memory and DOM
```javascript
self.remove("module_id");
```

####self.model
Set/gets 2Way model linked with Current View module instance.
```javascript
self.model({ score : 50 });

var score  = self.model().score;
//score is 50

self.model().score = 40;

```








