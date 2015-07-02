# View Module


Each module which has its own independant DOM presence. They are called view.

\_view\_ is actually shortcut for extending _view_ (or _spamjs.module_) module. Its each instance has its own life cycle and predefined methods.

###Life Cycle
```javascript
_view_("mychatwindow",function(mychatwindow,_mychatwindow_){

    _mychatwindow_._init_ = function(appConfig){
        console.log("View is Intialized");
    };

    _mychatwindow_._remove_ = function(){
        console.log("View is being removed from DOM");
    };

});
```
###Methods
####self.view
Sets the view for module instance
```javascript
self.view({ //Same as self.load
    src : "relative_path_to_my_html",
    data : "relative_path_to_my_json" | {PlainObject} | Promise(),
    html : "<div></div>" //Optional if src is not given
});

//OR
self.view(
    "relative_path_to_my_html",
    "relative_path_to_my_json" | {PlainObject} | Promise()
});
```
####self.data
set/get data for module
```javascript
self.data({
    name : "Lalit Tanwar"
});

```

####self.render
set/get data for module and re-render html again.
```javascript
self.render({
    name : "Lalit Tanwar"
});
```

####self.html
set/get html for module and re-render html again.
```javascript
self.html("<div>Hello</div>");
```

####self.add
removes child module from memory and DOM
```javascript
var CHILD_MODULE = _module_("child.module");

self.add(CHILD_MODULE.instance({
    id : "myID"
}));

```

####self.addTo
Ideally used to initialize top-most view which has not parent, and in absence of param will use body as container.
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

###Properties

#####self.$$
jQuery DOM reference object for current view module instance
```javascript
self.$$.find(".myname").text("LNT");

```



