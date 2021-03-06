# View Module

###### package#module - spamjs/view#spamjs.view

A module having its own independant DOM presence is referred as **View**

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
        },
        function_name1 : function(e,target,data){
            //mybutton been clicked
            //e - event
            // target - target element which got clicked
            //data - dataset for target element
        },
        function_name3 : function(e,target,data){
            //my2button been clicked
            //e - event
            // target - target element which got clicked
            //data - dataset for target element
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
    id : "myID",
    options : {
         key : "VALUE"
    }
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
Note:- if no arguments is passed modules itself get removed

####self.model
Set/gets 2Way model linked with Current View module instance.
```javascript
self.model({ score : 50 });

var score  = self.model().score;
//score is 50

self.model().score = 40;

```


###Events

####\_init\_
```javascript

        _init_ : function(appConfig){
            //When View is Attached to DOM tree
            console.log("View is Intialized");
            this.$$.html("<div>Hello</div>");

            //Or set html from file
            var absoluteTemplatePath = this.path("relative/path/to/template.html")
            this.$$.loadTemplate(absoluteTemplatePath)
            //or in single statment
            this.$$.loadTemplate(this.path("relative/path/to/template.html"))

            //Or to pass data to template
            this.$$.loadTemplate(
                this.path("relative/path/to/template.html"),
                { fname : "lalit", lname : "Tanwar"}
            );

            //Alternativley instead of data a promise can be provided
            // In this case template will be rendered after data is fetched from server
            this.$$.loadTemplate(
                this.path("relative/path/to/template.html"),
                jQuery.get("/data/getUserDetails")
            );


        }```









